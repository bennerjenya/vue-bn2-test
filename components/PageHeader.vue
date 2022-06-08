<template>
  <header class="header">
    <section class="top-bar">
      <h2 class="visually-hidden">
        Top bar
      </h2>
      <span class="top-bar__info">special deals <a class="top-bar__link" href="/">link</a></span>
      <ul class="top-links">
        <li class="top-links__item">
          <a class="top-links__link">first</a>
        </li>
        <li class="top-links__item">
          <a class="top-links__link">second</a>
        </li>
        <li class="top-links__item">
          <a class="top-links__link">third</a>
        </li>
        <li class="top-links__item">
          <a class="top-links__link">fourth</a>
        </li>
      </ul>
    </section>
    <nav class="main-navigation">
      <div class="logo">
        <a href="/"><img src="/logo.png" alt="ГдеМатериал.Ру"></a> <!--TODO(iNerV) do dynamically link-->
      </div>
      <div class="main-navigation__burger">
        <button class="main-navigation__open-menu-btn" @click="toggleMenu">
          {{ menuIsOpen ? 'Close' : 'Menu' }}
        </button>
      </div>
      <div class="main-navigation__search">
        <input class="main-navigation__input" type="search" placeholder="search">
      </div>
      <ul class="user-box">
        <li class="user-box__item">
          <a class="user-box__link" href="#user">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12.035 12.825C10.778 12.825 9.54934 12.4519 8.50456 11.7531C7.45977 11.0542 6.6459 10.061 6.16602 8.89923C5.68615 7.73746 5.56187 6.45941 5.80892 5.22696C6.05597 3.9945 6.66323 2.86309 7.5538 1.97603C8.44436 1.08897 9.57816 0.486169 10.8116 0.243983C12.045 0.00179788 13.3226 0.131121 14.4824 0.615574C15.6423 1.10003 16.6323 1.91781 17.327 2.96535C18.0218 4.01288 18.39 5.24304 18.385 6.5C18.3758 8.17898 17.703 9.78618 16.5134 10.9711C15.3239 12.156 13.714 12.8224 12.035 12.825ZM12.035 0.625003C10.8791 0.625014 9.74902 0.967488 8.78754 1.6092C7.82606 2.2509 7.07625 3.16308 6.63275 4.23057C6.18925 5.29806 6.07195 6.47302 6.29566 7.60712C6.51936 8.74122 7.07404 9.78362 7.88968 10.6027C8.70532 11.4219 9.74535 11.981 10.8785 12.2095C12.0116 12.4381 13.1871 12.3258 14.2564 11.8868C15.3258 11.4479 16.2412 10.702 16.887 9.74325C17.5328 8.78452 17.8801 7.65595 17.885 6.5C17.887 5.73004 17.7372 4.96723 17.4442 4.25518C17.1512 3.54313 16.7208 2.8958 16.1775 2.35019C15.6342 1.80458 14.9887 1.37139 14.2779 1.07537C13.5671 0.779353 12.805 0.626314 12.035 0.625003V0.625003Z" fill="#FFFFFF"/>
              <path d="M23.09 23.725H1.09003V21.545C1.09267 19.112 2.06001 16.7793 3.77994 15.0584C5.49987 13.3376 7.83202 12.369 10.265 12.365H13.91C16.3435 12.369 18.6762 13.3374 20.3969 15.0581C22.1176 16.7789 23.0861 19.1115 23.09 21.545V23.725ZM1.59003 23.225H22.59V21.545C22.5874 19.2437 21.672 17.0375 20.0448 15.4102C18.4175 13.783 16.2113 12.8676 13.91 12.865H10.265C7.96376 12.8676 5.75751 13.783 4.13026 15.4102C2.50302 17.0375 1.58767 19.2437 1.58503 21.545L1.59003 23.225Z" fill="#FFFFFF"/>
            </svg>
          </a>
        </li>
        <li class="user-box__item">
          <a class="user-box__link" href="#basket">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M20.15 19.685H6.355C6.07488 19.6853 5.80413 19.5842 5.59275 19.4003C5.38137 19.2165 5.24364 18.9624 5.205 18.685L3.77 6.615C3.76752 6.59025 3.75589 6.56731 3.7374 6.55067C3.71891 6.53403 3.69488 6.52488 3.67 6.525H1.33C1.086 6.525 0.851999 6.42807 0.679465 6.25554C0.506932 6.083 0.410004 5.849 0.410004 5.605V5.405C0.41394 5.16361 0.512603 4.93344 0.684712 4.76414C0.856821 4.59483 1.08858 4.49997 1.33 4.5H3.855C4.32708 4.50124 4.78251 4.67457 5.13595 4.98752C5.4894 5.30046 5.7166 5.73155 5.775 6.2L7.155 17.545C7.16209 17.5905 7.18505 17.632 7.21983 17.6623C7.2546 17.6925 7.29895 17.7094 7.345 17.71H20.15C20.4152 17.71 20.6696 17.8154 20.8571 18.0029C21.0446 18.1904 21.15 18.4448 21.15 18.71C21.15 18.9752 21.0446 19.2296 20.8571 19.4171C20.6696 19.6046 20.4152 19.71 20.15 19.71V19.685ZM1.33 5C1.22126 5 1.11698 5.0432 1.04009 5.12009C0.9632 5.19698 0.920004 5.30126 0.920004 5.41V5.61C0.920004 5.71874 0.9632 5.82302 1.04009 5.89991C1.11698 5.9768 1.22126 6.02 1.33 6.02H3.67C3.8195 6.02024 3.9637 6.07536 4.07523 6.17491C4.18676 6.27446 4.25785 6.41149 4.275 6.56L5.71 18.61C5.72951 18.7673 5.80585 18.9121 5.92463 19.0171C6.04342 19.122 6.19648 19.18 6.355 19.18H20.15C20.2581 19.1529 20.3541 19.0905 20.4226 19.0026C20.4912 18.9147 20.5285 18.8065 20.5285 18.695C20.5285 18.5835 20.4912 18.4753 20.4226 18.3874C20.3541 18.2995 20.2581 18.2371 20.15 18.21H7.345C7.1751 18.2091 7.01122 18.1469 6.88352 18.0349C6.75582 17.9228 6.6729 17.7684 6.65 17.6L5.27 6.25C5.2273 5.90487 5.05986 5.58727 4.79922 5.35703C4.53859 5.12679 4.20277 4.99981 3.855 5H1.33Z" fill="#FFFFFF"/>
              <path d="M20.295 16.085H6.5L5.395 7.12002H21.86C21.9945 7.11901 22.1274 7.14866 22.2487 7.2067C22.37 7.26475 22.4764 7.34967 22.56 7.45502C22.6461 7.55854 22.7071 7.68052 22.7383 7.81147C22.7695 7.94242 22.7701 8.07881 22.74 8.21002L21.175 15.38C21.1297 15.5798 21.0181 15.7583 20.8582 15.8863C20.6984 16.0144 20.4998 16.0844 20.295 16.085V16.085ZM6.905 15.615H20.295C20.3922 15.6134 20.4861 15.5797 20.5621 15.5191C20.638 15.4585 20.6918 15.3744 20.715 15.28L22.28 8.11002C22.2928 8.04744 22.2919 7.98282 22.2772 7.92065C22.2625 7.85849 22.2345 7.80026 22.195 7.75002C22.1547 7.70002 22.1036 7.65969 22.0457 7.632C21.9877 7.60432 21.9242 7.58997 21.86 7.59002H5.925L6.905 15.615Z" fill="#FFFFFF"/>
              <path d="M7.37 22.315H7.305C7.09988 22.3079 6.89819 22.2603 6.71156 22.1749C6.52493 22.0895 6.35705 21.968 6.21761 21.8174C6.07816 21.6668 5.96991 21.49 5.8991 21.2974C5.82828 21.1048 5.7963 20.9 5.805 20.695C5.82377 20.2819 6.0032 19.8926 6.305 19.61C6.53155 19.4001 6.81546 19.2624 7.12054 19.2145C7.42562 19.1666 7.73806 19.2106 8.01803 19.3409C8.29801 19.4713 8.53283 19.682 8.69258 19.9463C8.85232 20.2106 8.92975 20.5165 8.915 20.825C8.89952 21.2273 8.72903 21.6082 8.43921 21.8877C8.14939 22.1673 7.76269 22.324 7.36 22.325L7.37 22.315ZM7.37 19.67C7.09775 19.6685 6.83507 19.7703 6.635 19.955C6.4762 20.1001 6.36415 20.2892 6.31308 20.4982C6.26201 20.7072 6.27423 20.9267 6.34818 21.1287C6.42214 21.3308 6.55449 21.5063 6.72843 21.6329C6.90236 21.7595 7.11001 21.8316 7.325 21.84C7.61276 21.8519 7.89348 21.749 8.10539 21.554C8.31731 21.3589 8.44307 21.0877 8.455 20.8C8.46694 20.5122 8.36407 20.2315 8.16903 20.0196C7.97399 19.8076 7.70276 19.6819 7.415 19.67H7.37V19.67Z" fill="#FFFFFF"/>
              <path d="M19.57 22.315H19.5C19.2949 22.308 19.0932 22.2604 18.9066 22.1749C18.7199 22.0895 18.5521 21.968 18.4126 21.8174C18.2732 21.6668 18.1649 21.4901 18.0941 21.2975C18.0233 21.1048 17.9913 20.9001 18 20.695C18.0094 20.438 18.0823 20.1874 18.212 19.9653C18.3417 19.7433 18.5243 19.5567 18.7436 19.4223C18.9628 19.2879 19.2119 19.2098 19.4686 19.1949C19.7253 19.18 19.9818 19.2288 20.2151 19.337C20.4484 19.4451 20.6514 19.6093 20.8059 19.8148C20.9604 20.0204 21.0617 20.261 21.1008 20.5152C21.1399 20.7693 21.1156 21.0292 21.0299 21.2717C20.9443 21.5142 20.8 21.7318 20.61 21.905C20.3291 22.1706 19.9566 22.3175 19.57 22.315ZM19.57 19.67C19.3567 19.6668 19.1471 19.7266 18.9676 19.8418C18.788 19.9571 18.6464 20.1227 18.5605 20.318C18.4746 20.5133 18.4482 20.7296 18.4846 20.9399C18.5209 21.1501 18.6185 21.3449 18.765 21.5C18.8613 21.6056 18.9776 21.691 19.1073 21.7511C19.2369 21.8112 19.3772 21.8448 19.52 21.85C19.6625 21.8563 19.8048 21.8344 19.9388 21.7856C20.0729 21.7369 20.196 21.6622 20.3011 21.5658C20.4063 21.4695 20.4915 21.3534 20.5517 21.2241C20.612 21.0949 20.6463 20.955 20.6525 20.8125C20.6587 20.6701 20.6369 20.5277 20.5881 20.3937C20.5393 20.2597 20.4646 20.1366 20.3683 20.0314C20.272 19.9263 20.1559 19.8411 20.0266 19.7808C19.8974 19.7205 19.7575 19.6863 19.615 19.68L19.57 19.67Z" fill="#FFFFFF"/>
            </svg>
          </a>
        </li>
      </ul>
      <div class="main-navigation__list" :class="(menuIsOpen ? 'main-navigation__list--opened' : '')">
        <ul>
          <TreeItem
            v-for="(item, index) in menu"
            :key="index"
            class="item"
            :model="item"
            :link-start="`/catalog`"
            :link-end="`${item.slug}`"
          />
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
import TreeItem from './TreeItem';

export default {
  name: 'PageHeader',
  components: {
    TreeItem,
  },
  data() {
    return {
      menu: [],
      menuIsOpen: false,
    };
  },
  mounted() {
    this.menu = this.$store.state.the_menu.menu;
  },
  methods: {
    toggleMenu() {
      this.menuIsOpen = !this.menuIsOpen;
      document.body.classList.toggle('noScroll');
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~assets/variables.scss";

.top-bar {
  display: flex;
  justify-content: space-between;
  background-color: rgb(96, 4, 186);
  color: rgb(255, 255, 255);
  font-size: .875rem;
  font-weight: 600;
  line-height: 19px;
  padding: .25rem 1rem;
  z-index: 2;

  &__info {
    font-weight: 900;
  }

  &__link {
    font-weight: normal;
  }
}

.top-links {
  display: flex;
  list-style-type: none;

  &__items {
    display: flex;
    padding: 0;
    list-style-type: none;
    font-size: .875rem;
    line-height: 19px;
  }

  &__item:not(:first-child) {
    margin-left: 15px;
  }
}

.main-navigation {
  display: grid;
  align-items: center;
  position: relative;
  grid-template-areas:
    "burger logo user-box"
    "search search search";
  grid-template-columns: 100px 1fr 100px;
  grid-template-rows: auto;
  padding: 1rem;
  background-color: rgb(130, 0, 255);
  color: rgb(255, 255, 255);
  z-index: 1;
  line-height: 2.5rem;

  @media (min-width: $screen-md) {
    grid-template-areas: "logo burger search user-box";
    grid-template-columns: 100px 100px 4fr 1fr;
    grid-gap: 1rem;
    //height: 57px;
  }

  &__burger {
    grid-area: burger;
    display: flex;
  }

  &__open-menu-btn {
    width: 100%;
    background: transparent;
    padding: .5rem 1.5rem;
    display: inline-block;
    border: 1px solid rgb(255, 255, 255);
    border-radius: 2px;
    position: relative;
    color: rgb(255, 255, 255);
    z-index: 1;
  }

  &__search {
    grid-area: search;
    color: rgb(68, 68, 68);
    display: none;
    @media (min-width: $screen-md) {
      display: block;
    }
  }

  &__input {
    width: 100%;
    height: 38px;
    text-align: left;
    overflow: hidden;
    padding: .45rem 1.5rem .45rem .5rem;
    line-height: 24px;
  }

  &__list {
    position: absolute;
    top: 100%;right: -100%;
    max-height: calc(100vh - 104px);
    overflow-y: auto;
    width: 100vw;
    transition: all .3s linear;
    padding: 1rem;
    background: #6004ba;
    z-index: 9999;
    &--opened {
      right: 0;
    }
  }

  & .logo {
    display: flex;
    & a {
      height: 100%;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}

.user-box {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  list-style-type: none;

  &__items {
    display: flex;
    padding: 0;
    list-style-type: none;
    font-size: .875rem;
    line-height: 19px;
  }
  &__link {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__item:not(:first-child) {
    margin-left: 15px;
  }
}

</style>
