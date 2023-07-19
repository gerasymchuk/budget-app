<template>
  <div class="top-navbar">
    <img src="@/assets/notification-linear.svg" alt="Notification" />
    <img src="@/assets/settings-linear.svg" alt="Settings" />
    <img src="@/assets/user-linear.svg" alt="User" />
  </div>
</template>

<style scoped>
.top-navbar {
  display: flex;
  align-items: flex-start;
  gap: 2rem;
}
.top-navbar img {
  width: 1.5rem;
  height: 1.5rem;
  flex: none;
  order: 0;
  flex-grow: 0;
}
</style>
