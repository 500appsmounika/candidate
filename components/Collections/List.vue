<template>
    <!--show the candidate list-->
<div class="mt-8 flow-root">
      <div class="-mx-4 -my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
        <div class="inline-block min-w-full py-2 align-middle sm:px-6 lg:px-8">
          <div class="overflow-hidden shadow ring-1 ring-black ring-opacity-5 sm:rounded-lg">
            <table class="min-w-full divide-y divide-gray-300">
              <thead class="bg-gray-50">
                <tr>
                  <th scope="col" class="py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-6">Name</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">Description</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">Type</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">Difficulty Level</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">max_time_allowed</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">due_date</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">multiple_attempts_allowed</th>
                  <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">status</th>
                  <th scope="col" class="relative py-3.5 pl-3 pr-4 sm:pr-6">
                  </th>
                </tr>
              </thead>
              <tbody class="divide-y divide-gray-200 bg-white">
                <tr v-for="template in templatedata" :key="template.name">
                  <td class="whitespace-nowrap py-4 pl-4 pr-3 text-sm font-medium text-gray-900 sm:pl-6">{{ template.name }}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.description }}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.type }}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.difficulry_level}}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.max_time_allowed}}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.due_date}}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.multiple_attempts_allowed}}</td>
                  <td class="whitespace-nowrap px-3 py-4 text-sm text-gray-500">{{ template.status}}</td>
                  <td class="relative whitespace-nowrap py-4 pl-3 pr-4 text-right text-sm font-medium sm:pr-6">
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
</template>
<script setup>
//define the props
const props = defineProps({
  templatedata: Array,
  default: () => [],
});
</script>