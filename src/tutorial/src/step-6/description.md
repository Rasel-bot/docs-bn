# Conditional Rendering {#conditional-rendering}

শর্তসাপেক্ষে একটি উপাদান রেন্ডার করতে আমরা `v-if` নির্দেশ ব্যবহার করতে পারি:

```vue-html
<h1 v-if="awesome">Vue is awesome!</h1>
```

এই `<h1>` শুধুমাত্র যদি `awesome` এর মান [সত্য](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) হয় তবেই রেন্ডার করা হবে। যদি `awesome` একটি [মিথ্যা](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) মানতে পরিবর্তিত হয়, তাহলে এটি DOM থেকে সরানো হবে।

আমরা শর্তের অন্যান্য শাখাগুলি বোঝাতে `v-else` এবং `v-else-if` ব্যবহার করতে পারি:

```vue-html
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```

বর্তমানে, ডেমো একই সময়ে `<h1>` উভয়ই দেখাচ্ছে, এবং বোতাম কিছুই করে না। তাদের সাথে `v-if` এবং `v-else` নির্দেশাবলী যোগ করার চেষ্টা করুন এবং `toggle()` পদ্ধতিটি প্রয়োগ করুন যাতে আমরা তাদের মধ্যে টগল করতে বোতামটি ব্যবহার করতে পারি।

`v-if` বিষয়ে আরও বিশদ বিবরণ: <a target="_blank" href="/guide/essentials/conditional.html">গাইড - শর্তসাপেক্ষ রেন্ডারিং</a>
