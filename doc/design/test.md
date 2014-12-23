sft-app-client.jar:

class Head {
    String acc_id;
    String version;
    String tcode;
    String ssn;
    String ttime;
    String tdate;
}

## 金融请求类
class AuthRequest        { String hmac; Head head; Body AuthBody; }
class PayRequest         { String hmac; Head head; ...}
class GatherRequest      { String hmac; Head head; ...}

class BatchPayRequest    { String hmac; Head head; ...}
class BatchGatherRequest { String hmac; Head head; ...}
class BatchAuthRequest   { String hmac; Head head; ...}

## 同步应答类: 就只有一个
class Response {}

查询类的交易都是同步的
class GatherQueryRespone {}
class PayQueryResponse {}
class AuthQueryResponse {}

class BatchPayQueryReponse {}
class BatchGatherQueryResponse {}
class BatchAuthQueryResponse {}

## 异步应答类:
class AuthResponse {}
class PayResponse {}
class GatherResponse {}

class BatchPayResponse {}
class BatchGatherResponse {}
class BatchAuthResponse {}


SFTClient client = new SFTClient('http://192.168.1.11/interface');

1>  单笔/批量: 代收、代付、(4)
Response resp = client.auth(authRequest);
Response resp = client.gather(gatherRequest);
Response resp = client.pay(payRequest);

Response resp = client.gatherBatch(gatherBatchRequest);
Response resp = client.payBatch(payBatchReqeust);
Response resp = client.authBatch(authBatchRequest);

2>  查询交易
AuthResponse    authResp          = client.authQuery(authQueryReq);
BathAuthReponse bathAuthResp      = client.batchAuthQuery(authQueryReq);

payQueryResp         = client.payQuery(payQueryReq)
batchPayQueryResp    = client.payBatchQuery(payBatchQueryReq);

gatherQueryResp      = client.gatherQuery(gatherQueryReq);
batchGatherQueryResp = client.batchGatherQuery(batchGatherQueryReq);

3> 异步回调接口:
if( tcode == '2001') {   // 代收
   GatherResponse gatherResp = JSONUtil.toObject(jsonResp)
}
elsif(tcode == '3001') {  // 代付
  PayResponse payResp = JSONUtil.toObject(jsonResp)
}
elsif( tcode = '1001') {  // 身份验证
  AuthResponse authResp = JSONUtil.toObject(jsonResp);
}
elsif( tcode == '2011') {}
elsif( tcode == '2011') {}
elsif( tcode == '2011') {}
elsif( tcode == '2011') {}


###############################################
sft-app-server.jar:

SFTServer server = new SFTServer();

server.checkMac(body);
