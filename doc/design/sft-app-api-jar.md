```java

class head {
  String version; // 版本号
  String tcode;   // 单笔代收
  String accId;   // 接入机构代码
  String ssn;     // 机构流水号
  String tdate;   // 机构交易日期
  String ttime;   //  机构交易时间
}

package com.smartpay.sft.api.request
package com.smartpay.sft.api.response
class Pay {

}

class Auth {
  String callback;
  String acctName => '周超',                 // 账户名称
  String acctNo   => '6226882100198883',    // 账号
  String bankCode => 'CCB',             //  ICCB CMB

  //////////////////////////////
  // 可选字段  idNo  ===>  id_no
  //////////////////////////////
  String idNo;
  String phone;
  String checkcode;
  String cvv;
  String expire;
}

class Gather {

}

class BatchPay {

}

class BatchAuth {

}

class BatchGather {

}

class Query {

}







```
Pay pay = new Pay();
pay.setCallback()
pay.setC..()
...

Head head = new Head();
head.setXXX().
...

Request req = new Request();
req.setHead()；
req.setBody();

Response res = Client.send(req)


//
