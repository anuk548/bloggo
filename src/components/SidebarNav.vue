<template>
	<aside 
		:className="`fixed top-0 left-0 min-h-screen pt-16 z-40 w-full max-w-xs transform duration-300 bg-gray-800 ${
			menu_is_active 
			? 'translate-x-0' 
			: '-translate-x-full'
        }`">
        <div className="p-4">
			<h2 className="text-gray-500 text-sm font-bold uppercase mb-2">MENU</h2>
            <div className="-mx-4">
				<MenuItem to="/">
					<span className="material-icons mr-2">home</span>Home
				</MenuItem>
				<MenuItem to="/authors">
					<span className="material-icons mr-2">groups</span> Authors
				</MenuItem>
			</div>
        </div>
	</aside>
</template>

<script>
import { computed } from 'vue';
import { useStore } from 'vuex';
import MenuItem from './MenuItem.vue';

export default {
	components: {
		MenuItem
    },
    setup () {
        const store = useStore()
       
        return {
            menu_is_active: computed(()=> store.state.menu_is_active)
        }
    }
}
</script>