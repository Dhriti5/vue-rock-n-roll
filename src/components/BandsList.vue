<template>
    <div>
    <input type="text" placeholder="Add band..." v-model="newBand"></input>
    <button @click="addBand">Add</button>
        <ul>
            <BandItem v-for="band in bands"  v-bind:band="band">
            </BandItem>
        </ul>
    </div>
</template>

<script>
import BandItem from '@/components/BandItem.vue'

export default{
name: 'BandList',
 components: {
    BandItem
  },
    data(){
    return{
        index : 2,
        bands:[
            {
                id: 1,
                name:'Black Sabbath',
                songs:['Paranoid', 'into the void']
            },{
                id: 2,
                name: 'Maroon 5',
                 songs:['Sugar', 'Girls like you']
            }
        ]
    }
},
methods:{
    addBand(){
        this.index++;
        var bandItem = {id: this.index,
        name: this.newBand,
        songs: []
        }
        this.bands.push(bandItem)
        this.newBand=''
    }
}

}
</script>
