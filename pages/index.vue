<template>
  <div
    class="
      principal
      min-h-screen
      bg-gradient-to-r
      from-violet-500
      to-fuchsia-500
      pb-4
    "
  >
    <div class="container mx-auto px-8 py-2 w-1/2">
      <div
        class="
          form
          bg-white/25
          shadow-2xl
          my-24
          flex flex-col
          items-center
          rounded-lg
          py-4
        "
      >
        <h1 class="text-2xl font-bold tracking-wide text-slate-800">
          Formulario Principal
        </h1>
        <form
          action=""
          class="py-4"
          :v-model="user"
          @submit.prevent="save('form', user)"
        >
          <label
            class="block my-4 font-bold font-sans tracking-wide text-gray-600"
            >Ingrese el nombre :</label
          >
          <input
            v-model="user"
            type="text"
            id="nombre"
            class="
              rounded
              shadow
              border
              py-1
              px-3
              leading-tight
              block
              my-4
              appearance-none
              focus:outline-none focus:shadow-outline
            "
            placeholder="Nombre"
          />
          <button
            class="bg-blue-500 text-white py-1 px-8 rounded w-full"
            type="submit"
          >
            Ingresar
          </button>
        </form>
      </div>
    </div>

    <div
      class="
        container
        mx-auto
        px-8
        py-8
        w-9/12
        bg-white/25
        shadow-2xl
        rounded
      "
    >
      <div class="flex flex-col">
        <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
          <div
            class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8"
          >
            <div
              class="
                shadow
                overflow-hidden
                border-2 border-gray-400
                sm:rounded-lg
              "
            >
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th
                      scope="col"
                      class="
                        px-6
                        py-3
                        text-left text-xs
                        font-medium
                        text-gray-500
                        uppercase
                        tracking-wider
                      "
                    >
                      ID
                    </th>
                    <th
                      scope="col"
                      class="
                        px-6
                        py-3
                        text-left text-xs
                        font-medium
                        text-gray-500
                        uppercase
                        tracking-wider
                      "
                    >
                      Name
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, i) in items" :key="i">
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">
                            {{i+1}}
                          </div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-900">
                        {{item.name}}
                      </div>
                    </td>
                  </tr>

                  <!-- More people... -->
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Principa",
  data() {
    return {
      user: "",
      items: [],
    };
  },
  methods: {
    save(formname, user) {
      this.items.push( {name:user});
      this.user = "";
    },
  },
};
</script>