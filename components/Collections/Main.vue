<template>
  <div class="flex align item-center">
    <h2 class="px-10">Candidate details</h2>

    <button
      type="button"
      class="rounded bg-indigo-50 px-2 py-1 text-sm font-semibold text-indigo-600 shadow-sm hover:bg-indigo-100"
      @click="opensidebar()"
    >
      +
    </button>
  </div>
  <CollectionsAdd
    v-if="open"
    :open="open"
    :formdata="formdata"
    @post-data="postData"
  ></CollectionsAdd>
  <CollectionsList  :templatedata="templateData"></CollectionsList>
</template>
<script setup >

const open = ref(false);
const templateData=ref([])
const formdata = {
  name: "",
  type:"",
  description: "",
  difficulty_level: "",
  max_time_allowed:"",
  due_date:"",
  multiple_attempts_allowed:0,
  status: 0,
};

//Post
const postData = async (form) => {
  let options = {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Accept: "application/json",
      Authorization:
        "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1IjoiYmZlOTY3MDc0YzJhNGVlNDhiODFlYWU1ZmU5ZThhMjkiLCJkIjoiMTY4MDA4MSIsInIiOiJzYSIsInAiOiJmcmVlIiwiYSI6ImZpbmRlci5pbyIsImwiOiJ1czEiLCJleHAiOjE2ODMyNzkyNzB9._HklK6rl9AWu3mp4kRdrOIsxyEP-jNpG7kgF3K-5GlA",
    },
    body:form
  };
 const data= await useAuthLazyFetchPost(
    "https://v7-stark-db-orm.mercury.infinity-api.net/api/mock-interviews/",
    options
  );
   templateData.value=data.data._rawValue
}
//get
const getData = useAuthLazyFetch(
  "https://v7-stark-db-orm.mercury.infinity-api.net/api/mock-interviews/?offset=0&limit=100&sort_column=id&sort_direction=desc"
);
templateData.value = getData.data._rawValue;
console.log("get--",templateData)
function opensidebar() {
  open.value = !open.value;
}
</script>
