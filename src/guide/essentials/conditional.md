# Conditional Rendering {#conditional-rendering}

<div class="options-api">
  <VueSchoolLink href="https://vueschool.io/lessons/conditional-rendering-in-vue-3" title="বিনামূল্যে Vue.js Conditional Rendering পাঠ"/>
</div>

<div class="composition-api">
  <VueSchoolLink href="https://vueschool.io/lessons/vue-fundamentals-capi-conditionals-in-vue" title="বিনামূল্যে Vue.js Conditional Rendering পাঠ"/>
</div>

<script setup>
import { ref } from 'vue'
const awesome = ref(true)
</script>

## `v-if` {#v-if}

নির্দেশিকা `v-if` শর্তসাপেক্ষে একটি ব্লক রেন্ডার করতে ব্যবহৃত হয়। নির্দেশের অভিব্যক্তি একটি সত্য মান প্রদান করলেই ব্লকটি রেন্ডার করা হবে।

```vue-html
<h1 v-if="awesome">Vue is awesome!</h1>
```

## `v-else` {#v-else}

আপনি `v-if` এর জন্য একটি "অন্য ব্লক" নির্দেশ করতে `v-else` নির্দেশিকা ব্যবহার করতে পারেন:

```vue-html
<button @click="awesome = !awesome">Toggle</button>

<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```

<div class="demo">
  <button @click="awesome = !awesome">Toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
</div>

<div class="composition-api">

[চেষ্টা করুন](https://sfc.vuejs.org/#eyJBcHAudnVlIjoiPHNjcmlwdCBzZXR1cD5cbmltcG9ydCB7IHJlZiB9IGZyb20gJ3Z1ZSdcblxuY29uc3QgYXdlc29tZSA9IHJlZih0cnVlKVxuPC9zY3JpcHQ+XG5cbjx0ZW1wbGF0ZT5cbiAgPGJ1dHRvbiBAY2xpY2s9XCJhd2Vzb21lID0gIWF3ZXNvbWVcIj50b2dnbGU8L2J1dHRvbj5cblxuXHQ8aDEgdi1pZj1cImF3ZXNvbWVcIj5WdWUgaXMgYXdlc29tZSE8L2gxPlxuXHQ8aDEgdi1lbHNlPk9oIG5vIPCfmKI8L2gxPlxuPC90ZW1wbGF0ZT4iLCJpbXBvcnQtbWFwLmpzb24iOiJ7XG4gIFwiaW1wb3J0c1wiOiB7XG4gICAgXCJ2dWVcIjogXCJodHRwczovL3NmYy52dWVqcy5vcmcvdnVlLnJ1bnRpbWUuZXNtLWJyb3dzZXIuanNcIlxuICB9XG59In0=)

</div>
<div class="options-api">

[চেষ্টা করুন](https://sfc.vuejs.org/#eyJBcHAudnVlIjoiPHNjcmlwdD5cbmV4cG9ydCBkZWZhdWx0IHtcbiAgZGF0YSgpIHtcbiAgXHRyZXR1cm4ge1xuXHQgICAgYXdlc29tZTogdHJ1ZVxuICBcdH1cblx0fVxufVxuPC9zY3JpcHQ+XG5cbjx0ZW1wbGF0ZT5cbiAgPGJ1dHRvbiBAY2xpY2s9XCJhd2Vzb21lID0gIWF3ZXNvbWVcIj50b2dnbGU8L2J1dHRvbj5cblxuXHQ8aDEgdi1pZj1cImF3ZXNvbWVcIj5WdWUgaXMgYXdlc29tZSE8L2gxPlxuXHQ8aDEgdi1lbHNlPk9oIG5vIPCfmKI8L2gxPlxuPC90ZW1wbGF0ZT4iLCJpbXBvcnQtbWFwLmpzb24iOiJ7XG4gIFwiaW1wb3J0c1wiOiB7XG4gICAgXCJ2dWVcIjogXCJodHRwczovL3NmYy52dWVqcy5vcmcvdnVlLnJ1bnRpbWUuZXNtLWJyb3dzZXIuanNcIlxuICB9XG59In0=)

</div>

একটি `v-else` উপাদান অবিলম্বে একটি `v-if` বা `v-else-if` উপাদান অনুসরণ করতে হবে - অন্যথায় এটি স্বীকৃত হবে না।

## `v-else-if` {#v-else-if}

`v-else-if`, নাম অনুসারে, `v-if`-এর জন্য একটি "else if block" হিসেবে কাজ করে। এটি একাধিকবার শৃঙ্খলিত হতে পারে:

```vue-html
<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
```

`v-else` এর মতো, একটি `v-else-if` উপাদান অবিলম্বে একটি `v-if` বা `v-else-if` উপাদান অনুসরণ করতে হবে।

## `v-if` on `<template>` {#v-if-on-template}

কারণ `v-if` একটি নির্দেশিকা, এটি একটি একক উপাদানের সাথে সংযুক্ত করতে হবে। কিন্তু যদি আমরা একাধিক উপাদান টগল করতে চাই? এই ক্ষেত্রে আমরা একটি `<template>` উপাদানে `v-if` ব্যবহার করতে পারি, যা একটি অদৃশ্য মোড়ক হিসেবে কাজ করে। চূড়ান্ত রেন্ডার করা ফলাফলে `<template>` উপাদান অন্তর্ভুক্ত হবে না।

```vue-html
<template v-if="ok">
  <h1>Title</h1>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</template>
```

`v-else` এবং `v-else-if` এছাড়াও `<template>` এ ব্যবহার করা যেতে পারে।

## `v-show` {#v-show}

শর্তসাপেক্ষে একটি উপাদান প্রদর্শনের জন্য আরেকটি বিকল্প হল `v-show` নির্দেশিকা। ব্যবহার মূলত একই:

```vue-html
<h1 v-show="ok">Hello!</h1>
```

পার্থক্য হল `v-show` সহ একটি উপাদান সর্বদা রেন্ডার করা হবে এবং DOM-এ থাকবে; `v-show` শুধুমাত্র এলিমেন্টের `display` CSS প্রপার্টি টগল করে।

`v-show` `<template>` উপাদানকে সমর্থন করে না, বা এটি `v-else`-এর সাথে কাজ করে না।

## `v-if` vs. `v-show` {#v-if-vs-v-show}

`v-if` হল "বাস্তব" শর্তসাপেক্ষ রেন্ডারিং কারণ এটি নিশ্চিত করে যে কন্ডিশনাল ব্লকের মধ্যে ইভেন্ট শ্রোতা এবং child উপাদানগুলি সঠিকভাবে ধ্বংস করা হয়েছে এবং টগল করার সময় পুনরায় তৈরি করা হয়েছে৷

`v-if`ও **অলস**: যদি শর্তটি প্রাথমিক রেন্ডারে মিথ্যা হয়, তবে এটি কিছুই করবে না - শর্তটি প্রথমবার সত্য না হওয়া পর্যন্ত শর্তযুক্ত ব্লক রেন্ডার করা হবে না।

তুলনামূলকভাবে, `v-show` অনেক সহজ - CSS-ভিত্তিক টগলিংয়ের সাথে প্রাথমিক অবস্থা নির্বিশেষে উপাদানটি সর্বদা রেন্ডার করা হয়।

সাধারণভাবে বলতে গেলে, `v-if`-এর টগল খরচ বেশি থাকে যখন `v-show`-এর প্রাথমিক রেন্ডার খরচ বেশি থাকে। তাই আপনি যদি প্রায়শই কিছু টগল করতে চান তাহলে `v-show` পছন্দ করুন এবং রানটাইমে অবস্থার পরিবর্তনের সম্ভাবনা না থাকলে `v-if` পছন্দ করুন।

## `v-if` with `v-for` {#v-if-with-v-for}

::: warning বিঃদ্রঃ
অন্তর্নিহিত অগ্রাধিকারের কারণে একই এলিমেন্টে `v-if` এবং `v-for` ব্যবহার করার পরামর্শ **নয়**। বিস্তারিত জানার জন্য [style guide](/style-guide/rules-essential.html#avoid-v-if-with-v-for) পড়ুন।
:::

যখন `v-if` এবং `v-for` উভয়ই একই উপাদানে ব্যবহৃত হয়, `v-if` প্রথমে মূল্যায়ন করা হবে। বিস্তারিত জানার জন্য [list rendering guide](list#v-for-with-v-if) দেখুন।
