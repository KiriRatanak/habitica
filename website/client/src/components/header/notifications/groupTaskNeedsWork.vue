<template>
  <base-notification
    :can-remove="canRemove"
    :has-icon="false"
    :notification="notification"
    :read-after-click="true"
    @click="action"
  >
    <div
      slot="content"
      class="notification-yellow"
      v-html="notification.data.message"
    ></div>
  </base-notification>
</template>

<script>
import BaseNotification from './base';

export default {
  components: {
    BaseNotification,
  },
  props: ['notification', 'canRemove'],
  methods: {
    action () {
      const groupId = this.notification.data.group.id;
      this.$router.push({ name: 'groupPlanDetailTaskInformation', params: { groupId } });
    },
  },
};
</script>
