// For the main Presets page to pass data into so that we can render the details on the browser page
<template>
    <div class="bg-lime-50">
        <div class="bg-white text-center py-5" v-if="this.profiles.length === 0">You don't have any profiles. Start by adding one!</div>
        <!-- loop through the profiles array to output a single profile component -->
        <div :key="profile.id" v-for="profile in profiles">
            <!-- catch the toggle-select emit from Profile child component and emit this event to the Preset parent component. Same for toggle-select -->
            <Profile @toggle-select="$emit('toggle-select', profile.id)" @delete-profile="$emit('delete-profile', profile.id)" :profile='profile' :selected='selected'/>
        </div>
    </div>
</template>

<script>
import Profile from './Profile.vue'
export default{
    name: 'Profiles',
    props: {
        profiles: Array,
        selected: Object
    },
    components: {
        Profile
    },
    // since we are taking the emit form the Profile child component and passing it to the Preset parent component
    emits: ['delete-profile', 'toggle-select']
}
</script>
<style>
</style>