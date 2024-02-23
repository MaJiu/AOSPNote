## BufferQueueCore

```C++
class BufferQueueCore : public virtual RefBase {
    typedef Vector<BufferItem> Fifo;
    // mSlots is an array of buffer slots that must be mirrored on the producer
    // side. This allows buffer ownership to be transferred between the producer
    // and consumer without sending a GraphicBuffer over Binder. The entire
    // array is initialized to NULL at construction time, and buffers are
    // allocated for a slot when requestBuffer is called with that slot's index.
    BufferQueueDefs::SlotsType mSlots;

    // mQueue is a FIFO of queued buffers used in synchronous mode.
    Fifo mQueue;

    // mFreeSlots contains all of the slots which are FREE and do not currently
    // have a buffer attached.
    std::set<int> mFreeSlots;

    // mFreeBuffers contains all of the slots which are FREE and currently have
    // a buffer attached.
    std::list<int> mFreeBuffers;

    // mUnusedSlots contains all slots that are currently unused. They should be
    // free and not have a buffer attached.
    std::list<int> mUnusedSlots;

    // mActiveBuffers contains all slots which have a non-FREE buffer attached.
    std::set<int> mActiveBuffers;
    
    // 构造函数
    // BufferQueueCore 的初始状态
    BufferQueueCore::BufferQueueCore() {
        int numStartingBuffers = getMaxBufferCountLocked();
        for (int s = 0; s < numStartingBuffers; s++) {
            mFreeSlots.insert(s);
        }
        for (int s = numStartingBuffers; s < BufferQueueDefs::NUM_BUFFER_SLOTS;
                s++) {
            mUnusedSlots.push_front(s);
        }
    }
}
```

mSlots used  unused

used active unactive

unactive  mFreeSlots mFreeBuffers

## SurfaceComposerClient

### Transaction

```C++
```

## LayerState.h

