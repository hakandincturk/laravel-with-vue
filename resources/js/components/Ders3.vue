<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Class - Style İşlemleri
                    </div>
                    <div class="card-body">
                        <p v-bind:style="myStyle">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                            Sed doloremque ratione unde possimus voluptatem natus maxime, 
                            obcaecati laborum illo reprehenderit, similique perspiciatis quo excepturi ipsa est quam distinctio. 
                            Incidunt, necessitatibus!</p>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data:()=>({
        name:'',
        myStyle:{
            color:'red',
            fontSize:'56px',
        }
    })
}
</script>

<style>
    
</style>