##

## 接入队列web.in
head + body

## 应答队列web.out
head + body

## 调度队列sched
json:
{
  batch_no => acc_id + ssn,

  chnl_batch => [
     {
       chnl_code => 'chnl_code_1',
       logs => [
         {}
         {}
       ]
     },

     {
       chnl_code => 'chnl_code_1',
       logs => [
         {}
         {}
        ]
     }
   ]
}

# 渠道队列

## ccb.gd
log

## ccb.gx

## tlt

## hyl


# 通知队列:
1>
