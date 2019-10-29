<template>
    <div class="card ">
        <div class="card-header">
            <ul class="nav nav-tabs card-header-tabs"  role="tablist">
                <li class="nav-item">
                    <a class="nav-link active" id="write-tab" data-toggle="tab" :href="tabId('write', '#')" role="tab" aria-controls="write" aria-selected="true">Write</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" id="preview-tab" data-toggle="tab" :href="tabId('preview', '#')" role="tab" aria-controls="preview" aria-selected="false">Preview</a>
                </li>
            </ul>
        </div>
        <div class="tab-content" id="myTabContent">
            <div class="tab-pane fade show active" :id="tabId('write')" role="tabpanel" aria-labelledby="write-tab">
                <slot></slot>
            </div>
            <div class="tab-pane fade" v-html="preview" :id="tabId('preview')" role="tabpanel" aria-labelledby="preview-tab"></div>
        </div>
    </div>
</template>

<script>
    import MarkdownIt from 'markdown-it';
    import prism from 'markdown-it-prism';
    import autosize from 'autosize';
    import 'prismjs/themes/prism.css';
    const md=new MarkdownIt();
    //md.use(prism); ha problemi , da risolvere
    export default {
        props: ['body', 'name'],
        computed:{
           preview(){
               return md.render(this.body);
           }
        },
        /*watch:{
           body:function(){
               console.log('watch body');
           }
        },

        mounted(){
            autosize(this.$el.querySelector('textarea'));
        },

         */

        methods: {
            tabId(tabName, hash = '') {
                return `${hash}${tabName}${this.name}`;
            },
        },
        updated(){
           autosize(this.$el.querySelector('textarea'));
        }
    }
</script>

<style scoped>

</style>
