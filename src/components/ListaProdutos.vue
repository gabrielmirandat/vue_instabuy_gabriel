<template>
  <div v-if="status === 'success'">
    <lista :items="itens_lista"/>
  </div>
</template>

<script>
import Lista from './objects/List'

export default {
  name: 'lista-produtos',
  components: {
    Lista
  },
  data () {
    return {
      status: false,
      itens_lista: {}
    }
  },
  created: function () {
    this.$http.get('https://instabuy.com.br/apiv2_2/product.json',
      {params: {subcategory_id: '57eec92f072d415b67c24175'}})
      .then(resposta => {
        this.status = resposta.data.status
        this.itens_lista = resposta.data.data.map(item => ({
          id: item.id,
          imagem: 'https://s3-us-west-2.amazonaws.com/ib.image.medium/m-' + item.thumb,
          marca: item.brand,
          nome: item.name,
          preco: item.pc[0].valid_price }))

        console.log(this.itens_lista)
      }, erro => {
        alert('Erro ao obter itens da lista!')
      })
  },
  methods: {
  }
}
</script>
