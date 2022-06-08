<template>
  <li>
    <div class="menu-link-holder" :class="{ bold: isSubmenu }" @click="toggle">
      <a class="menu-link" :to="`${fullLink}`">
        {{ model.name }}
      </a>
      <span v-if="isSubmenu" class="arrow" :class="(isOpen ? 'toggled' : '')">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd"
                d="M12 14.0859L5.70706 7.79297L4.29285 9.20718L12 16.9143L19.7071 9.20718L18.2928 7.79297L12 14.0859Z"
                fill="#B2B8C6"
          />
        </svg>
      </span>
    </div>
    <ul v-if="isSubmenu" class="menu__list" :class="(isOpen ? 'menu__list--opened' : '')">
      <TreeItem
        v-for="(item, index) in model.submenu"
        :key="index"
        class="item"
        :model="item"
        :link-start="fullLink"
        :link-end="model.slug"
      />
    </ul>
  </li>
</template>

<script>
export default {
  name: 'TreeItem',
  props: {
    model: {
      type: Object,
      default() {
        return {};
      },
      submenu: {
        type: Object,
        default() {
          return {};
        },
      },
      slug: {
        type: String,
        default: '',
      },
    },
    linkStart: {
      type: String,
      default: '',
    },
    linkEnd: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      isOpen: false,
    };
  },
  computed: {
    fullLink() {
      return `${this.linkStart}/${this.linkEnd}`;
    },
    isSubmenu() {
      return this.model.submenu && this.model.submenu.length;
    },
  },
  methods: {
    toggle() {
      if (this.isSubmenu) {
        this.isOpen = !this.isOpen;
      }
    },
  },
};
</script>

<style scoped lang="scss">
.bold {
  font-weight: bold;
}
.menu {
  &__list {
    max-height: 0;
    overflow: hidden;
    -webkit-transition: max-height 0.3s;
    -moz-transition: max-height 0.3s;
    transition: max-height 0.3s;
    &--opened {
      max-height: 1000px;
      transition-delay: 150ms;
    }
  }
}
.menu-link {
  font-size: 14px;
  line-height: 18px;
}

.menu-link-holder {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 0;
}
.arrow {
  display: flex;
  align-items: center;
  justify-content: center;
  & svg {
    transition: all .3s linear;
  }

  &.toggled {
    & svg {
      transform: rotate(180deg);
    }
  }
}
</style>
