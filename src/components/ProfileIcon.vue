<template>
  <div class="media-container" @click='showMenu' >
    <i class="fa-regular fa-user"></i>
    <transition name="fade-slide">
      <div v-if="isMenuVisible" class="dropdown-menu">
        <a href="https://www.twitch.tv/olesha" class="dropdown-item">
          <i class="fa-solid fa-gears"></i>
          <div class="about">
            <div class="title">В разработке</div>
          </div>
        </a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuVisible: false, // По умолчанию меню скрыто
    };
  },
  methods: {
    showMenu() {
      this.isMenuVisible = this.isMenuVisible === false ? true : false;
    },
  }
};
</script>

<style scoped>
/* Стили для контейнера */
.media-container {
  position: relative;
  background: none;
  border: none;
  color: var(--text-secondary-color);
  cursor: pointer;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

/* Стили для выпадающего меню */
.dropdown-menu {
  position: absolute;
  top: 230%;
  right: -1em;
  background-color: var(--dark-sm-clear-md);
  border: 1px solid var(--border-color);
  border-radius: var(--border-radius-md);
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  display: flex;
  flex-direction: column;
  min-width: 250px; /* Минимальная ширина меню */
  z-index: 50; /* Чтобы меню было поверх других элементов */
  backdrop-filter: blur(3px);
  padding: 7px;
  transition: all 0.3s ease; /* 5. Анимируем только прозрачность */
}

/* Стили для ссылок в меню */
.dropdown-menu a {
  padding: 10px 15px;
  text-decoration: none;
  color: #ffffff;
  border-radius: var(--border-radius-md);
}

.dropdown-menu a:hover {
  background-color: #3c3c3c;
}

.media-container:hover {
  color: var(--text-color);
}
.media-container i {
  z-index: 1;
}
.dropdown-item {
  display: flex;
}
.dropdown-item img {
  height: 40px;
  margin-right: 10px;
  border-radius: 50%;
}
.about {
  width: auto;
  justify-content: center;
}
.title {
  padding-bottom: 5px;
}
.description {
  font-size: 0.7rem;
}
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 2.2);
}

.fade-slide-enter-from,
.fade-slide-leave-to {
  opacity: 0;
  transform: translateY(-5px);
}

</style>