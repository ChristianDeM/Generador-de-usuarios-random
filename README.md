# Generador-de-usuarios-random

El siguiente proyecto esta echo con

- Vue cdn
- js
- api `` https://randomuser.me/ ``
- Bootstrap

## Codigo 

- user.js

```
 const app  = Vue.createApp({
    data() {
      return {
        Titulo: 'Generador de usuarios',
        name:'que onda',
        nombre:'Nombre random',
        apellido:'Apellido random',
        correo:'correo random',
        telefono:'Telefono random',
        direccion:'Direccion random',
        genero:'genero random',
        foto:'https://randomuser.me/api/portraits/men/75.jpg'
      }
    },

    methods:{
     async imprimirnombre(){
        const info  =  await fetch('https://randomuser.me/api/');
        const rinfo = await info.json()
        console.log(rinfo)

        
        this.nombre = rinfo.results[0].name.first
        this.apellido =rinfo.results[0].name.last
        this.correo= rinfo.results[0].email
        this.telefono =rinfo.results[0].phone
        this.direccion =rinfo.results[0].location.city
        this.genero = rinfo.results[0].gender
        this.foto = rinfo.results[0].picture.large

      }
    }
  })

app.mount('#app');
```

