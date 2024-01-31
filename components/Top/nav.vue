<script setup>
const obj = ref(null)
const title = ref("")
const props = defineProps({
  itemsMenu: {
    type: Array,
    default: () => []
    // required: true
  }
})
async function logData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  obj.value = await response.json();
  title.value = obj.value ? " - " + obj.value.title : "";
  console.log(obj.value.title);
}

onMounted(() => {
  console.log(props.itemsMenu);
})

logData();
</script>

<template>
   <nav class="navbar navbar-expand-lg bg-white navbar-light shadow sticky-top p-0">
        <a href="index.html" class="navbar-brand d-flex align-items-center px-4 px-lg-5">
            <h2 class="m-0 text-primary"><i class="fa fa-car me-3"></i>CarServ{{ title }}</h2>
        </a>
        <button type="button" class="navbar-toggler me-4" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
            <span class="navbar-toggler-icon"></span>
        </button>
          <div class="collapse navbar-collapse justify-content-between" id="navbarCollapse">
        <div class="navbar-nav ml-auto">
          <NuxtLink v-for="item of itemsMenu" :to="item.to" class="nav-item nav-link">{{ item.name }}</NuxtLink>
        </div>
      </div>
    </nav>
  <!-- Nav Bar End -->
</template>