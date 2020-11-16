<template>
  <div class="hello">
    <h1>{{ msg | capitalize }}</h1>
    <pre><a :href="url">EVE Api</a></pre>
  </div>
</template>
 
<script>
export default {
  name: "hello",
  data() {
    return {
      msg: "jim MK II",
      url: "https://esi.evepc.163.com/",
      info: null,
    };
  },
};
</script>