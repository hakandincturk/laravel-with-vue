<template>
  <div v-if="users.length > 0" class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Users
                    </div>
                    <div class="card-body">
                        <li :key="key" v-for="(user, key) in users">
                            {{user}}
                            <button class="btn btn-danger btn-sm mb-2" @click="$emit('deleteUser', key)">Sil</button>
                        </li>
                    </div>
                </div>
            </div>
</template>

<script>
export default {
    props:['users']
}
</script>

<style>

</style>