单笔身份认证
请求
```javascript
{
  head => {
    tcode   => 'auth',                   // 认证
    inst_id  => '99990001',              // 接入机构代码
    ssn     => 'NNNNNN',                 // 请求流水号
    tdate   => '20141212',               // 机构交易日期
    ttime   => '121212',                 // 机构交易时间
    callback => 'http://cb'              // 回调
  },
  body => {
    acct_name => '周超',                 // 账户名称
    acct_no   => '6226882100198883',    // 账号
    id_no     => '430681198212302914',  // 身份证号
    phone     => '18874881230',         // 选填
    checkcode => '888888',              // 短信校验码(optional)
  }
}
```

应答
```javascript
{
  head => {
    tcode   => 'auth',        // 认证
    inst_id  => '99990001',    //
    ssn     => 'NNNNNN'       //
    tdate   => '20141212',    //
    ttime   => '121212',      //
  },
  body => {
    resp_code => '000000'     // 成功
  }
}
```


单笔代收(2001)
请求
```javascript
{
  head => {
    version => '1.0',
    tcode   => 'gather',    // 代收交易
    acc_id  => '99990001',
    ssn     => '20141212121212NNNNNN'
    tdate   => '20141212',
    ttime   => '121212',
    callback => 'http://192.168.1.1/sft/callback',
  },
  body => {
    btype => '保险',
    tamt  => '9999',
    currency => '156',

    acct_cat => '1',
    acct_name => '周超',
    acct_no   => '6226882100198883',
    id_no     => '430681198212302914'
  }
}
```
应答
```javascript
{
  head => {
    tcode   => 'gather',    // 代收交易
    inst_id  => '99990001',
    ssn     => '20141212121212NNNNNN'
    tdate   => '20141212',
    ttime   => '121212',
  },
  body => {
    resp_code  => '000000',   // 成功
    bank_ssn   => 'NNNNNN'    //
    bank_tdate => 'YYYYMMDD', //
    bank_ttime => 'HHMMSS',   //

    //
    btype     => '0006',
    tamt      => '9999',
    acct_cat  => '1',
    acct_name => '周超',
    acct_no   => '6226882100198883',
  }
}
```

单笔代付
请求
```javascript

{
  head => {
    tcode   => 'pay',    // 代付交易
    acc_id  => '99990001',
    ssn     => '20141212121212NNNNNN'
    tdate   => '20141212',
    ttime   => '121212',
    callback => 'http://cb'
  },
  body => {
    tamt  => '9999',
    acct_cat => '1',
    acct_name => '周超',
    acct_no   => '6226882100198883',
    bank_no   => '联行号'
    bank_name => '开户行名称'
  }
}
```
应答
```javascript
{
  head => {
    tcode   => 'pay',    // 代付交易
    acc_id  => '99990001',
    ssn     => '20141212121212NNNNNN'
    tdate   => '20141212',
    ttime   => '121212',
  },
  body => {
    resp_code => '000000', // 成功
    sft_ssn => 'NNNNNN'
    sft_tdate => 'YYYYMMDD',
    sft_ttime => 'HHMMSS',

    tamt  => '9999',
    acct_cat => '1',
    acct_name => '周超',
    acct_no   => '6226882100198883',
    bank_no   => '联行号'
    bank_name => '开户行名称'
    pay_memo  => '付款备注'
  }
}
```
