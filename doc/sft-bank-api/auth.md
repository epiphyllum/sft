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
