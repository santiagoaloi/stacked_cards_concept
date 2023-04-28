<template>
  <FlexContainerCard>
    <template #header>
      <VCard elevation="8">
        <VBtn color="indigo-lighten-2" @click="addCard"> Add Card </VBtn>
      </VCard>
    </template>

    <div>
      <VRow v-if="cards.length" class="ma-auto">
        <VCol v-for="card in cards" :key="card.id" cols="4">
          <VCard class="pa-5" elevation="8" height="250" width="100%">
            <div class="d-flex flex-column fill-height">
              <div class="d-flex fill-height flex-column">
                <VCardTitle> Task {{ card.id }} </VCardTitle>
                <VCardText>
                  {{ card.body }}
                </VCardText>
              </div>
              <div class="d-flex fill-height mt-auto align-end">
                <VBtn color="indigo" size="small" @click="removeCard(card.id)">Remove</VBtn>
              </div>
            </div>
          </VCard>
        </VCol>
      </VRow>
    </div>
  </FlexContainerCard>
</template>
<script setup>
import { v4 as uuidv4 } from 'uuid'

function addCard() {
  const newCard = {
    id: uuidv4(),
    body: 'to make a type specimen book. It has survived not only five centto make a type  to make a type specimen book. It has survived not only five cent'
  }

  cards.value.push(newCard)
}

function removeCard(id) {
  cards.value = cards.value.filter((card) => {
    return card.id !== id
  })
}

const cards = ref([
  {
    id: uuidv4(),
    body: 'to make a type specimen book. It has survived not only five centto make a type specimen book. It has survived not only five cent to make a type specimen book. It has survived not only five cent'
  }
])
</script>
