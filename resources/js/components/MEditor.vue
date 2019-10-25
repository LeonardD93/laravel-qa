<template>
    <div class="card ">
        <div class="card-header">
            <ul class="nav nav-tabs card-header-tabs"  role="tablist">
                <li class="nav-item">
                    <a class="nav-link active" id="write-tab" data-toggle="tab" href="#write" role="tab" aria-controls="write" aria-selected="true">Write</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" id="preview-tab" data-toggle="tab" href="#preview" role="tab" aria-controls="preview" aria-selected="false">Preview</a>
                </li>
            </ul>
        </div>
        <div class="tab-content" id="myTabContent">
            <div class="tab-pane fade show active" id="write" role="tabpanel" aria-labelledby="write-tab">  <slot></slot> </div>
            <div class="tab-pane fade" v-html="preview" id="preview" role="tabpanel" aria-labelledby="preview-tab"></div>
        </div>
    </div>
</template>

<script>
    import MarkdownIt from 'markdown-it';
    const md=new MarkdownIt();
    export default {
       props:['body'],
        computed:{
           preview(){
               return md.render(this.body);
           }
        }
    }
</script>

<style scoped>

</style>
