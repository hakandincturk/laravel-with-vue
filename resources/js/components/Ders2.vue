<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Form İşlemleri
                    </div>
                    <div class="card-body">
                        <div class="form-group">
                            <label>Ad</label>
                            {{name}}
                            <input class="form-control" type="text" v-model.lazy="name"/>
                        </div>

                        <div class="form-group">
                            <span :key="key" v-for="(singular, key) in select">
                                {{options.find(item=>item.value == singular).name}}
                            </span>
                            <select class="form-control" multiple v-model="select">
                                <option :value="option.value" :key="key" v-for="(option, key) in options">
                                    {{option.name}}
                                </option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label>{{radio}}</label>
                            <label for="bir">Elma</label><input type="radio" id="bir" value="0" v-model="radio"/>
                            <label for="iki">Armut</label><input type="radio" id="iki" value="1" v-model="radio"/>
                        </div>

                        <div class="form-group">
                            <label>{{checkbox}}</label>
                            <label for="elma">Elma</label><input type="checkbox" id="elma" value="Elma" v-model="checkbox">
                            <label for="armut">Armut</label><input type="checkbox" id="armut" value="Armut" v-model="checkbox">
                            <label for="kiraz">Kiraz</label><input type="checkbox" id="kiraz" value="Kiraz" v-model="checkbox">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data:()=>({
        name:null,
        options:[
            {name:'Belirtmek İstemiyorum', value:'0'},
            {name:'Erkek', value:'1'},
            {name:'Kadın', value:'2'}
        ],
        select:[0,1],
        radio:null,
        checkbox:[]
    })
}
</script>

<style>

</style>