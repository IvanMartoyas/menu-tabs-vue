<template>
      <div class="wrapper">
        <div id="tabs-wrapper" class="tabs__block">
            <div class="tabMenu__button"></div>
            <div class="tabs tabMenu">
              <span class="tab tabMenu__item" v-for="item in menu_items" :key="item" v-show="item.active" @click="setComponent(item.slug)">{{item.title}}</span>
            </div>
            <div class="tabs-content tabContent">
                <div class="tab-item tabContent__item">
                    <component :is="componentId"></component>
                </div>
            </div>
        </div>
      </div>
</template>
<script>
import { _menu_items } from '@/components/Tabs_menu/_menu.js'; // пункты меню
import General_parameters from '@/views/General_parameters.vue';
import Size_panel from '@/views/Size_panel.vue';
import Version_pillar from '@/views/Version_pillar.vue';
import Additional_elements_fence from '@/views/Additional_elements_fence.vue';
import Wickets from '@/views/Wickets.vue';
import Gates from '@/views/Gates.vue';
import General_view_fence from '@/views/General_view_fence.vue';

export default {
    name: "Tab",
    components: {
        General_parameters,
        Size_panel,
        Version_pillar,
        Additional_elements_fence,
        Wickets,
        Gates,
        General_view_fence
    },
    data() {
        return {
            menu_items: [],
            componentId: '',
        }
    },
    mounted() {
        this.menu_items = _menu_items;
        this.componentId = _menu_items[0].slug;// активирую первый элемент из массива
        console.log
    },
    methods: {
        setComponent(slug) { 
            this.componentId = slug;
        },
    }
}
</script>
<style lang="scss">
   @import './style_tab.css';
</style>