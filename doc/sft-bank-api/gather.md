
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
