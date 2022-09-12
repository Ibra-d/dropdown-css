<template>
  <div class="nav">
    <li>
      <p>
        Landings
        <i class="fa-sharp fa-solid fa-chevron-right"></i>
      </p>

      <ul class="lu-der">
        <li>
          <a href="/">test& - link 1</a>
        </li>
        <li>
          <a href="/">test - link 2</a>
        </li>
        <li class="li-der">
          <a href="/">test - link 3</a>
          <ul>
            <li>
              <a href="/">test - link 4</a>
            </li>
            <li>
              <a href="/">test - link 5</a>
            </li>
            <li>
              <a href="/">test - link 6</a>
            </li>
          </ul>
        </li>
      </ul>
    </li>
    <li>
      <p>
        Landings
        <i class="fa-sharp fa-solid fa-chevron-right"></i>
      </p>
    </li>
    <li>
      <p>
        Landings
        <i class="fa-sharp fa-solid fa-chevron-right"></i>
      </p>
    </li>
    <li>
      <p>
        Landings
        <i class="fa-sharp fa-solid fa-chevron-right"></i>
      </p>
    </li>
    <a class="contact" href="mailto:drame.ibou.07@gmail.com">Contact</a>
  </div>
</template>

<script>
export default {
  name: "NavVue",
  setup() {
    //

    return {};
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../scss/_mixins.scss";

.nav {
  @include allFlex($justify: space-between);

  li {
    @include allFlex($justify: center);
    cursor: pointer;
    padding: 0 0.5em;
    margin: 0 0.5em;
    position: relative;

    p {
      @include allFlex($justify: center);
      gap: 0.3em;

      i {
        font-size: 9px;
        transition: 200ms;
      }
    }

    &:hover {
      .lu-der {
        visibility: visible;
        transform: translateY(0);
        opacity: 1;
      }

      i {
        transform: translateX(1em) rotate(90deg);
      }
    }

    .multi-child-toggle {
      visibility: visible;
    }

    .lu-der {
      transform: translateY(3em);
      transition: 300ms;
      visibility: hidden;
      opacity: 0;
      position: absolute;
      top: 100%;
      margin: 0;
      padding: 1em 0;
      background-color: #fff;
      @include allFlex($justify: center);
      flex-direction: column;
      border-radius: 0.5em;

      li {
        list-style: none;
        padding: 0.2em 1em;

        a {
          border-radius: 0.5em;
          transition: 200ms;
          @include allFlex($justify: center);
          width: 7em;
          color: black;
          text-decoration: none;
          padding: 0.5em 1em;
          // box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;

          &:hover {
            background-color: #578e65;
            color: #fff;
          }
        }
      }

      .li-der {
        ul {
          visibility: hidden;
          position: absolute;
          top: 6px;
          left: calc(100% + 1em);
          background-color: white;
          margin: 0;
          padding: 0;
          border-radius: 0 0.5em 0.5em;
          transform: translateY(3em);
          transition: 300ms;
          opacity: 0;

          &::before {
            content: "";
            position: absolute;
            height: 10px;
            width: 10px;
            top: 0;
            left: -5px;
            background-color: #fff;
            clip-path: polygon(0 0, 100% 100%, 100% 0);
          }
        }

        &:hover {
          ul {
            visibility: visible;
            transform: translateY(0);
            opacity: 1;
          }
        }
      }

      &::before {
        content: "";
        position: absolute;
        height: 10px;
        width: 10px;
        background-color: white;
        top: -5px;
        transform: rotate(45deg);
      }
    }
  }

  .contact {
    color: white;
    padding: 0.8em 1em;
    margin: 0 0 0 2em;
    border-radius: 0.5em;
    text-decoration: none;
    background-color: #578e65;
    transition: 200ms;

    &:hover {
      background-color: #005215;
    }
  }
}
</style>
