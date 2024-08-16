

+++
title = "arena.h"
toc_hide = "true"
linkTitle = "C++"
description = "This section contains reference documentation for working with protocol buffer classes in C++."
type = "docs"
+++

<p><code>#include &lt;google/protobuf/arena.h&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a></code></p><p>This file defines an <a href='#Arena'>Arena</a> allocator for better allocation performance. </p><table width="100%"><tr><th colspan="2"><h3 style="margin-top: 4px">Classes in this file</h3></th></tr><tr><td><div><code><a href="#ArenaOptions">ArenaOptions</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"><a href='#ArenaOptions'>ArenaOptions</a> provides optional additional parameters to arena construction that control its block-allocation behavior. </div></td></tr><tr><td><div><code><a href="#Arena">Arena</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"><a href='#Arena'>Arena</a> allocator. </div></td></tr><tr><td><div><code><a href="#Arena.InternalHelper">Arena::InternalHelper</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"></div></td></tr><tr><td><div><code><a href="#Arena.is_arena_constructable">Arena::is_arena_constructable</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Helper typetraits that indicates support for arenas in a type T at compile time. </div></td></tr><tr><td><div><code><a href="#Arena.is_destructor_skippable">Arena::is_destructor_skippable</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"></div></td></tr></table><h2 id="ArenaOptions">struct ArenaOptions</h2><p><code>#include &lt;<a href="#">google/protobuf/arena.h</a>&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a></code></p><p><a href='#ArenaOptions'>ArenaOptions</a> provides optional additional parameters to arena construction that control its block-allocation behavior. </p><table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>size_t</code></td><td style="border-left-width: 0px"id="ArenaOptions.start_block_size"><div style="padding-left: 16px; text-indent: -16px"><code><b>start_block_size</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">This defines the size of the first block requested from the system malloc.  <a href="#ArenaOptions.start_block_size.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>size_t</code></td><td style="border-left-width: 0px"id="ArenaOptions.max_block_size"><div style="padding-left: 16px; text-indent: -16px"><code><b>max_block_size</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">This defines the maximum block size requested from system malloc (unless an individual arena allocation request occurs with a size larger than this maximum).  <a href="#ArenaOptions.max_block_size.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>char *</code></td><td style="border-left-width: 0px"id="ArenaOptions.initial_block"><div style="padding-left: 16px; text-indent: -16px"><code><b>initial_block</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">An initial block of memory for the arena to use, or NULL for none.  <a href="#ArenaOptions.initial_block.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>size_t</code></td><td style="border-left-width: 0px"id="ArenaOptions.initial_block_size"><div style="padding-left: 16px; text-indent: -16px"><code><b>initial_block_size</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">The size of the initial block, if provided. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>void *(*</code></td><td style="border-left-width: 0px"id="ArenaOptions.block_alloc"><div style="padding-left: 16px; text-indent: -16px"><code><b>block_alloc</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">A function pointer to an alloc method that returns memory blocks of size requested.  <a href="#ArenaOptions.block_alloc.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>void(*</code></td><td style="border-left-width: 0px"id="ArenaOptions.block_dealloc"><div style="padding-left: 16px; text-indent: -16px"><code><b>block_dealloc</b></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">A function pointer to a dealloc method that takes ownership of the blocks from the arena.  <a href="#ArenaOptions.block_dealloc.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="ArenaOptions.ArenaOptions"><div style="padding-left: 16px; text-indent: -16px"><code><b>ArenaOptions</b>()</code></div></td></tr></table> <hr><h3 id="ArenaOptions.start_block_size.details"><code>size_t ArenaOptions::start_block_size</code></h3><div style="margin-left: 16px"><p>This defines the size of the first block requested from the system malloc. </p><p>Subsequent block sizes will increase in a geometric series up to a maximum. </p>
</div> <hr><h3 id="ArenaOptions.max_block_size.details"><code>size_t ArenaOptions::max_block_size</code></h3><div style="margin-left: 16px"><p>This defines the maximum block size requested from system malloc (unless an individual arena allocation request occurs with a size larger than this maximum). </p><p>Requested block sizes increase up to this value, then remain here. </p>
</div> <hr><h3 id="ArenaOptions.initial_block.details"><code>char * ArenaOptions::initial_block</code></h3><div style="margin-left: 16px"><p>An initial block of memory for the arena to use, or NULL for none. </p><p>If provided, the block must live at least as long as the arena itself. The creator of the <a href='#Arena'>Arena</a> retains ownership of the block after the <a href='#Arena'>Arena</a> is destroyed. </p>
</div> <hr><h3 id="ArenaOptions.block_alloc.details"><code>void *(* ArenaOptions::block_alloc</code></h3><div style="margin-left: 16px"><p>A function pointer to an alloc method that returns memory blocks of size requested. </p><p>By default, it contains a ptr to the malloc function.</p>

<p>NOTE: block_alloc and dealloc functions are expected to behave like malloc and free, including Asan poisoning. </p>
</div> <hr><h3 id="ArenaOptions.block_dealloc.details"><code>void(* ArenaOptions::block_dealloc</code></h3><div style="margin-left: 16px"><p>A function pointer to a dealloc method that takes ownership of the blocks from the arena. </p><p>By default, it contains a ptr to a wrapper function that calls free. </p>
</div><h2 id="Arena">class Arena</h2><p><code>#include &lt;<a href="#">google/protobuf/arena.h</a>&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a></code></p><p><a href='#Arena'>Arena</a> allocator. </p><p><a href='#Arena'>Arena</a> allocation replaces ordinary (heap-based) allocation with new/delete, and improves performance by aggregating allocations into larger blocks and freeing allocations all at once. Protocol messages are allocated on an arena by using Arena::CreateMessage&lt;T&gt;(Arena*), below, and are automatically freed when the arena is destroyed.</p>

<p>This is a thread-safe implementation: multiple threads may allocate from the arena concurrently. Destruction is not thread-safe and the destructing thread must synchronize with users of the arena first.</p>

<p>An arena provides two allocation interfaces: CreateMessage&lt;T&gt;, which works for arena-enabled proto2 message types as well as other types that satisfy the appropriate protocol (described below), and Create&lt;T&gt;, which works for any arbitrary type T. CreateMessage&lt;T&gt; is better when the type T supports it, because this interface (i) passes the arena pointer to the created object so that its sub-objects and internal allocations can use the arena too, and (ii) elides the object's destructor call when possible. Create&lt;T&gt; does not place any special requirements on the type T, and will invoke the object's destructor when the arena is destroyed.</p>

<p>The arena message allocation protocol, required by <a href='#Arena.CreateMessage'>CreateMessage&lt;T&gt;(Arena* arena, Args&amp;&amp;... args)</a>, is as follows:</p>

<ul>
  <li>The type T must have (at least) two constructors: a constructor callable with <code>args</code> (without <code>arena</code>), called when a T is allocated on the heap; and a constructor callable with <code>Arena* arena, Args&amp;&amp;... args</code>, called when a T is allocated on an arena. If the second constructor is called with a NULL arena pointer, it must be equivalent to invoking the first (<code>args</code>-only) constructor.</li>
  <li>The type T must have a particular type trait: a nested type |InternalArenaConstructable_|. This is usually a typedef to |void|. If no such type trait exists, then the instantiation CreateMessage&lt;T&gt; will fail to compile.</li>
  <li>The type T <i>may</i> have the type trait |DestructorSkippable_|. If this type trait is present in the type, then its destructor will not be called if and only if it was passed a non-NULL arena pointer. If this type trait is not present on the type, then its destructor is always called when the containing arena is destroyed.</li>
</ul>

<p>This protocol is implemented by all arena-enabled proto2 message classes as well as protobuf container types like <a href='../google.protobuf.repeated_field#RepeatedPtrField'>RepeatedPtrField</a> and <a href='../google.protobuf.map#Map'>Map</a>. The protocol is internal to protobuf and is not guaranteed to be stable. Non-proto types should not rely on this protocol. </p>

<table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>const size_t</code></td><td style="border-left-width: 0px"id="Arena.kBlockOverhead"><div style="padding-left: 16px; text-indent: -16px"><code><b>kBlockOverhead</b> = =
      internal::ThreadSafeArena::kBlockHeaderSize +
      internal::ThreadSafeArena::kSerialArenaSize</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Block overhead.  <a href="#Arena.kBlockOverhead.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="Arena.Arena"><div style="padding-left: 16px; text-indent: -16px"><code><b>Arena</b>()</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Default constructor with sensible default options, tuned for average use-cases. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="Arena.Arena"><div style="padding-left: 16px; text-indent: -16px"><code><b>Arena</b>(char * initial_block, size_t initial_block_size)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Construct an arena with default options, except for the supplied initial block.  <a href="#Arena.Arena.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>explicit </code></td><td style="border-left-width: 0px"id="Arena.Arena"><div style="padding-left: 16px; text-indent: -16px"><code><b>Arena</b>(const <a href='#ArenaOptions'>ArenaOptions</a> &amp; options)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"><a href='#Arena'>Arena</a> constructor taking custom options.  <a href="#Arena.Arena.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="Arena.~Arena"><div style="padding-left: 16px; text-indent: -16px"><code><b>~Arena</b>()</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>void</code></td><td style="border-left-width: 0px"id="Arena.Init"><div style="padding-left: 16px; text-indent: -16px"><code><b>Init</b>(const <a href='#ArenaOptions'>ArenaOptions</a> &amp; )</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>uint64</code></td><td style="border-left-width: 0px"id="Arena.SpaceAllocated"><div style="padding-left: 16px; text-indent: -16px"><code><b>SpaceAllocated</b>() const</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">The following are routines are for monitoring.  <a href="#Arena.SpaceAllocated.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>uint64</code></td><td style="border-left-width: 0px"id="Arena.SpaceUsed"><div style="padding-left: 16px; text-indent: -16px"><code><b>SpaceUsed</b>() const</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Returns the total space used by the arena.  <a href="#Arena.SpaceUsed.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>uint64</code></td><td style="border-left-width: 0px"id="Arena.Reset"><div style="padding-left: 16px; text-indent: -16px"><code><b>Reset</b>()</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Frees all storage allocated by this arena after calling destructors registered with <a href='#Arena.OwnDestructor'>OwnDestructor()</a> and freeing objects registered with <a href='#Arena.Own'>Own()</a>.  <a href="#Arena.Reset.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template void</code></td><td style="border-left-width: 0px"id="Arena.Own"><div style="padding-left: 16px; text-indent: -16px"><code><b>Own</b>(T * object)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Adds |object| to a list of heap-allocated objects to be freed with |delete| when the arena is destroyed or reset. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template void</code></td><td style="border-left-width: 0px"id="Arena.OwnDestructor"><div style="padding-left: 16px; text-indent: -16px"><code><b>OwnDestructor</b>(T * object)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Adds |object| to a list of objects whose destructors will be manually called when the arena is destroyed or reset.  <a href="#Arena.OwnDestructor.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>void</code></td><td style="border-left-width: 0px"id="Arena.OwnCustomDestructor"><div style="padding-left: 16px; text-indent: -16px"><code><b>OwnCustomDestructor</b>(void * object, void(*)(void *) destruct)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Adds a custom member function on an object to the list of destructors that will be manually called when the arena is destroyed or reset.  <a href="#Arena.OwnCustomDestructor.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template static T *</code></td><td style="border-left-width: 0px"id="Arena.CreateMessage"><div style="padding-left: 16px; text-indent: -16px"><code><b>CreateMessage</b>(<a href='#Arena'>Arena</a> * arena, Args &amp;&amp;... args)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">API to create proto2 message objects on the arena.  <a href="#Arena.CreateMessage.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template static PROTOBUF_NDEBUG_INLINE T *</code></td><td style="border-left-width: 0px"id="Arena.Create"><div style="padding-left: 16px; text-indent: -16px"><code><b>Create</b>(<a href='#Arena'>Arena</a> * arena, Args &amp;&amp;... args)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">API to create any objects on the arena.  <a href="#Arena.Create.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template static PROTOBUF_NDEBUG_INLINE T *</code></td><td style="border-left-width: 0px"id="Arena.CreateArray"><div style="padding-left: 16px; text-indent: -16px"><code><b>CreateArray</b>(<a href='#Arena'>Arena</a> * arena, size_t num_elements)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Create an array of object type T on the arena <i>without</i> invoking the constructor of T.  <a href="#Arena.CreateArray.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>template static <a href='#Arena'>Arena</a> *</code></td><td style="border-left-width: 0px"id="Arena.GetArena"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetArena</b>(const T * value)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Retrieves the arena associated with |value| if |value| is an arena-capable message, or NULL otherwise.  <a href="#Arena.GetArena.details">more...</a></div></td></tr></table> <hr><h3 id="Arena.kBlockOverhead.details"><code>const size_t Arena::kBlockOverhead = =
      internal::ThreadSafeArena::kBlockHeaderSize +
      internal::ThreadSafeArena::kSerialArenaSize</code></h3><div style="margin-left: 16px"><p>Block overhead. </p><p>Use this as a guide for how much to over-allocate the initial block if you want an allocation of size N to fit inside it.</p>
<p>WARNING: if you allocate multiple objects, it is difficult to guarantee that a series of allocations will fit in the initial block, especially if <a href='#Arena'>Arena</a> changes its alignment guarantees in the future! </p>
</div> <hr><h3 id="Arena.Arena.details"><code> Arena::Arena(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;char * initial_block,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;size_t initial_block_size)</code></h3><div style="margin-left: 16px"><p>Construct an arena with default options, except for the supplied initial block. </p><p>It is more efficient to use this constructor instead of passing <a href='#ArenaOptions'>ArenaOptions</a> if the only configuration needed by the caller is supplying an initial block. </p>
</div> <hr><h3 id="Arena.Arena.details"><code>explicit  Arena::Arena(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const <a href='#ArenaOptions'>ArenaOptions</a> &amp; options)</code></h3><div style="margin-left: 16px"><p><a href='#Arena'>Arena</a> constructor taking custom options. </p><p>See <a href='#ArenaOptions'>ArenaOptions</a> above for descriptions of the options available. </p>
</div> <hr><h3 id="Arena.SpaceAllocated.details"><code>uint64 Arena::SpaceAllocated() const</code></h3><div style="margin-left: 16px"><p>The following are routines are for monitoring. </p><p>They will approximate the total sum allocated and used memory, but the exact value is an implementation deal. For instance allocated space depends on growth policies. Do not use these in unit tests. Returns the total space allocated by the arena, which is the sum of the sizes of the underlying blocks. </p>
</div> <hr><h3 id="Arena.SpaceUsed.details"><code>uint64 Arena::SpaceUsed() const</code></h3><div style="margin-left: 16px"><p>Returns the total space used by the arena. </p><p>Similar to SpaceAllocated but does not include free space and block overhead. The total space returned may not include space used by other threads executing concurrently with the call to this method. </p>
</div> <hr><h3 id="Arena.Reset.details"><code>uint64 Arena::Reset()</code></h3><div style="margin-left: 16px"><p>Frees all storage allocated by this arena after calling destructors registered with <a href='#Arena.OwnDestructor'>OwnDestructor()</a> and freeing objects registered with <a href='#Arena.Own'>Own()</a>. </p><p>Any objects allocated on this arena are unusable after this call. It also returns the total space used by the arena which is the sums of the sizes of the allocated blocks. This method is not thread-safe. </p>
</div> <hr><h3 id="Arena.OwnDestructor.details"><code>template void Arena::OwnDestructor(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;T * object)</code></h3><div style="margin-left: 16px"><p>Adds |object| to a list of objects whose destructors will be manually called when the arena is destroyed or reset. </p><p>This differs from <a href='#Arena.Own'>Own()</a> in that it does not free the underlying memory with |delete|; hence, it is normally only used for objects that are placement-newed into arena-allocated memory. </p>
</div> <hr><h3 id="Arena.OwnCustomDestructor.details"><code>void Arena::OwnCustomDestructor(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;void * object,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;void(*)(void *) destruct)</code></h3><div style="margin-left: 16px"><p>Adds a custom member function on an object to the list of destructors that will be manually called when the arena is destroyed or reset. </p><p>This differs from <a href='#Arena.OwnDestructor'>OwnDestructor()</a> in that any member function may be specified, not only the class destructor. </p>
</div> <hr><h3 id="Arena.CreateMessage.details"><code>template static T * Arena::CreateMessage(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='#Arena'>Arena</a> * arena,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Args &amp;&amp;... args)</code></h3><div style="margin-left: 16px"><p>API to create proto2 message objects on the arena. </p><p>If the arena passed in is NULL, then a heap allocated object is returned. Type T must be a message defined in a .proto file with cc_enable_arenas set to true, otherwise a compilation error will occur.</p>
<p><a href='../google.protobuf.repeated_field#RepeatedField'>RepeatedField</a> and <a href='../google.protobuf.repeated_field#RepeatedPtrField'>RepeatedPtrField</a> may also be instantiated directly on an arena with this method.</p>
<p>This function also accepts any type T that satisfies the arena message allocation protocol, documented above. </p>
</div> <hr><h3 id="Arena.Create.details"><code>template static PROTOBUF_NDEBUG_INLINE T * <br>&nbsp;&nbsp;&nbsp;&nbsp;Arena::Create(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='#Arena'>Arena</a> * arena,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Args &amp;&amp;... args)</code></h3><div style="margin-left: 16px"><p>API to create any objects on the arena. </p><p>Note that only the object will be created on the arena; the underlying ptrs (in case of a proto2 message) will be still heap allocated. Proto messages should usually be allocated with <a href='#Arena.CreateMessage'>CreateMessage&lt;T&gt;()</a> instead.</p>
<p>Note that even if T satisfies the arena message construction protocol (InternalArenaConstructable_ trait and optional DestructorSkippable_ trait), as described above, this function does not follow the protocol; instead, it treats T as a black-box type, just as if it did not have these traits. Specifically, T's constructor arguments will always be only those passed to <a href='#Arena.Create'>Create&lt;T&gt;()</a> &ndash; no additional arena pointer is implicitly added. Furthermore, the destructor will always be called at arena destruction time (unless the destructor is trivial). Hence, from T's point of view, it is as if the object were allocated on the heap (except that the underlying memory is obtained from the arena). </p>
</div> <hr><h3 id="Arena.CreateArray.details"><code>template static PROTOBUF_NDEBUG_INLINE T * <br>&nbsp;&nbsp;&nbsp;&nbsp;Arena::CreateArray(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='#Arena'>Arena</a> * arena,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;size_t num_elements)</code></h3><div style="margin-left: 16px"><p>Create an array of object type T on the arena <i>without</i> invoking the constructor of T. </p><p>If <code>arena</code> is null, then the return value should be freed with <code>delete[] x;</code> (or <code>::operator delete[](x);</code>). To ensure safe uses, this function checks at compile time (when compiled as C++11) that T is trivially default-constructible and trivially destructible. </p>
</div> <hr><h3 id="Arena.GetArena.details"><code>template static <a href='#Arena'>Arena</a> * Arena::GetArena(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const T * value)</code></h3><div style="margin-left: 16px"><p>Retrieves the arena associated with |value| if |value| is an arena-capable message, or NULL otherwise. </p><p>If possible, the call resolves at compile time. Note that we can often devirtualize calls to <code>value-&gt;<a href='#Arena.GetArena'>GetArena()</a></code> so usually calling this method is unnecessary. </p>
</div><h2 id="Arena.InternalHelper">template class Arena::InternalHelper</h2><p><code>#include &lt;<a href="#">google/protobuf/arena.h</a>&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a><br><br>template &lt;typename &gt;</code></p><p></p><table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static <a href='#Arena'>Arena</a> *</code></td><td style="border-left-width: 0px"id="Arena.InternalHelper.GetOwningArena"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetOwningArena</b>(const T * p)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Provides access to protected GetOwningArena to generated messages. </div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>static <a href='#Arena'>Arena</a> *</code></td><td style="border-left-width: 0px"id="Arena.InternalHelper.GetArenaForAllocation"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetArenaForAllocation</b>(const T * p)</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Provides access to protected GetArenaForAllocation to generated messages. </div></td></tr></table><h2 id="Arena.is_arena_constructable">template struct Arena::is_arena_constructable</h2><p><code>#include &lt;<a href="#">google/protobuf/arena.h</a>&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a><br><br>template &lt;typename &gt;</code></p><p>Helper typetraits that indicates support for arenas in a type T at compile time. </p><p>This is public only to allow construction of higher-level templated utilities.</p>
<p>is_arena_constructable&lt;T&gt;::value is true if the message type T has arena support enabled, and false otherwise.</p>
<p>is_destructor_skippable&lt;T&gt;::value is true if the message type T has told the arena that it is safe to skip the destructor, and false otherwise.</p>
<p>This is inside <a href='#Arena'>Arena</a> because only <a href='#Arena'>Arena</a> has the friend relationships necessary to see the underlying generated code traits. </p>
<table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr></table><h2 id="Arena.is_destructor_skippable">template struct Arena::is_destructor_skippable</h2><p><code>#include &lt;<a href="#">google/protobuf/arena.h</a>&gt;<br>namespace <a href="#google.protobuf">google::protobuf</a><br><br>template &lt;typename &gt;</code></p><p></p><table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr></table>