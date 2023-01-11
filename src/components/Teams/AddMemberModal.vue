<script setup>
import ModalVue from "../ModalVue.vue";
import { ref } from "vue";
import { useTeamStore } from "@/stores/TeamStore";
let showModal=ref(false)

let team=useTeamStore();

</script>

<template>
    <button class="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded disabled:bg-gray-400"
              :disabled=" ! team.spotsRemaining"
              @click="showModal=true"
              >Add Member ({{ team.spotsRemaining }} Spots Left)
        </button>
     <Teleport to="body">
        <ModalVue :show="showModal" @close="showModal = false">
            <template #default>
            <p>Do you need to add new member to your team?</p>
             <form class="mt-6 ">
                   <div class="flex gap-2">
                   <input type="email" placeholder="Eamil Address ..." class="flex-1 px-2" />
                <button class="= bg-blue-700 text-white px-1 rounded">Add</button>
                  </div>
             </form>     
            </template>
         </ModalVue>
    </Teleport>
</template>
