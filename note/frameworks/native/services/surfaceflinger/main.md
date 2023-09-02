## SurfaceFlinger

```C++
// Transaction

mutable Mutex mQueueLock;
Condition mTransactionQueueCV;
// pending 的 transaction 按 applyToken 分类
std::unordered_map<sp<IBinder>, std::queue<TransactionState>, IListenerHash>
        mPendingTransactionQueues GUARDED_BY(mQueueLock);
// 需要处理的 Transaction  按时间顺序入队
std::queue<TransactionState> mTransactionQueue GUARDED_BY(mQueueLock);

```

