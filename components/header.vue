<template>
    <b-navbar toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand>EXAM</b-navbar-brand>

        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
              <NuxtLink exact active-class="text-white" class="nav-link" to="/">Главная</NuxtLink>
              <NuxtLink active-class="text-white" class="nav-link" to="/post/">Посты</NuxtLink>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
                <b-nav-form>
                    <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                    <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
                </b-nav-form>
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>

</style>
