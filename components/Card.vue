<template >
    <div class="card w-84 md:w-96 bg-base-100 shadow-xl" style="margin: 2rem 0.55rem 0.55rem 0.55rem;">
        <figure><img src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" alt="Shoes" /></figure>
        <div class="card-body">
            <h2 class="card-title">
                {{tabDataApiJob.title}}
                <div class="badge" style="background-color:#58d9db; color:white">NEW</div>
            </h2>
            <p>Bouygue Telecom</p>
            <div class="card-actions justify-end">
                <div class="badge badge-outline">Paris</div> 
                <div class="badge badge-outline">  {{tabDataApiJob.type}}</div>
            </div>
        </div>
    </div>
</template>

<script> 
    export default {

            name:'Card',
            props: ['tabDataApiJob'],

            methods:{
                consoleLog : function(){
                    console.log(this.tabDataApiJob)
                }
            }
            
    }
</script>
