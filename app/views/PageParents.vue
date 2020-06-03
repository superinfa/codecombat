<template>
    <div>
        <button @click="subscribeModalOpen = true">Subscribe to Premium</button>
        <button @click="openDriftWelcomeCallPlaybook">Small Group Classes</button>
        <button @click="openDriftWelcomeCallPlaybook">Private Lessons</button>
        <backbone-modal-harness :modal-view="SubscribeModal" :open="subscribeModalOpen" @close="subscribeModalClosed" />
    </div>
</template>

<script>
  import SubscribeModal from 'views/core/SubscribeModal'
  import BackboneModalHarness from './common/BackboneModalHarness'

  export default {
    inject: ['openLegacyModal'],

    components: {
      BackboneModalHarness,
    },

    data: () => ({
      SubscribeModal,
      subscribeModalOpen: false
    }),

    methods: {
      openDriftWelcomeCallPlaybook () {
        window.drift.api.startInteraction({ interactionId: 161673 });
      },

      subscribeModalClosed() {
        this.subscribeModalOpen = false
      }
    }
  }
</script>

<style>

</style>
