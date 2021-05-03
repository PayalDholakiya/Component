<template>
  <div class="m-10">
    <form>
      <BaseInput
        class="mb-4"
        type="text"
        label="First Name: "
        v-model="firstname"
      />
      <BaseInput
        class="mb-4"
        type="text"
        label="Last Name: "
        v-model="lastname"
      />
      <BaseInput class="mb-4" type="email" label="Email" v-model="email" />
      <BaseInput
        class="mb-4"
        type="password"
        label="Password"
        v-model="password"
      />
      <div>
        <DropDown :options="categories" />
      </div>
    </form>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'
import BaseInput from '../components/BaseInput.vue'
import DropDown from '../components/Dropdown.vue'

export default {
  name: 'FormComponent',
  components: {
    BaseInput,
    DropDown,
  },
  setup() {
    const firstname = ref('')
    const lastname = ref('')
    const email = ref('')
    const password = ref('')
    const categories = reactive(['edit', 'archive', 'delete'])
    return { firstname, lastname, email, password, categories }
  },
}
</script>
