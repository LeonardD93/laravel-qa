<template>
    <div class="card ">
        <div class="card-header">
            <ul class="nav nav-tabs card-header-tabs"  role="tablist">
                <li class="nav-item">
                    <a class="nav-link active" id="home-tab" data-toggle="tab" href="#write" role="tab" aria-controls="home" aria-selected="true">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" id="profile-tab" data-toggle="tab" href="#preview" role="tab" aria-controls="profile" aria-selected="false">Profile</a>
                </li>
            </ul>
        </div>
        <div class="tab-content" id="myTabContent">
            <div class="tab-pane fade show active" id="write" role="tabpanel" aria-labelledby="home-tab">  <slot></slot> </div>
            <div class="tab-pane fade" id="preview" role="tabpanel" aria-labelledby="profile-tab">Preview...</div>
        </div>
    </div>
</template>

<script>
    export default {
       props:['body']
    }
</script>

<style scoped>

</style>
