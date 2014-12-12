单笔代付
请求
```javascript

{
  head => {
    tcode   => 'pay',    // 代付交易
    inst_id  => 'sft',
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
    inst_id => 'sft',
    ssn     => '20141212121212NNNNNN'
    tdate   => '20141212',
    ttime   => '121212',
  },
  body => {
    resp_code  => '000000', // 成功
    bank_ssn   => 'NNNNNN'
    bank_tdate => 'YYYYMMDD',
    bank_ttime => 'HHMMSS',

    tamt  => '9999',
    acct_cat => '1',
    acct_name => '周超',
    acct_no   => '6226882100198883',
  }
}
```
