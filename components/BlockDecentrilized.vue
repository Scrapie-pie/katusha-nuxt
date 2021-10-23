<script>
export default {
  name: 'BlockDecentrilized',
  render(h) {
    const [left, leftRoute] = this.initSide(this.$slots.left, 'left');
    const [right, rightRoute] = this.initSide(this.$slots.right, 'right');
    const top = this.initSide(this.$slots.top, 'top');

    return (
      <div class="decentralized">
        {left}
        <div class="decentralized__position_middle">
          {leftRoute}
          <div class="decentralized__main">
            {top}
            {...this.$slots.default}
          </div>
          {rightRoute}
        </div>
        {right}
      </div>
    )
  },
  methods: {
    wrapItems(slot, isAside) {
      return slot.map((item) => {
        const wrappedItem = () => {
          if (isAside) { return (
            <div class="decentralized__item">
              <div class="decentralized__content">
                {item}
              </div>
            </div>
          )} else { return (
            <div class="decentralized__content">
              {item}
            </div>
          )}
        }
        return wrappedItem();
      });
    },
    initSide(slot, side) {
      if (!slot) return [null, null];
      if (!['left', 'right', 'top'].includes(side)) return [null, null]

      if (side === 'top') { return (
        <div class="decentralized__route_top">
          {...this.wrapItems(slot)}
        </div>
      )} else return [
        <aside class={'decentralized__position_' + side}>
          {...this.wrapItems(slot, true)}
        </aside>,
        <div class={'decentralized__route_' + side}></div>
      ]
    }
  },
}
</script>

<style lang="scss">
.decentralized {
  $d: &;
  $border: 2px dashed black;
  $z1: 20px;
  $offset-radius: 20px + 4px;

  display: flex;
  justify-content: space-between;
  align-items: stretch;
  position: relative;
  width: 100%;
  height: 100%;

  &__included {
    width: 100%;
  }

  &__item {
    overflow: hidden;
    position: relative;
    &:after {
      content: '';
      position: absolute;
      width: 100%;
      border-bottom: $border;
      top: 50%;
      transform: translateY(-50%);
    }
    &:first-child {
      &:after {
        top: 20px;
        transform: none;
      }
    }
    &:last-child {
      &:after {
        top: auto;
        bottom: 20px;
        transform: none;
      }
    }
  }

  &__route {
    &_top {
      left: 45%;
      z-index: 1;
      max-width: 165px;
      position: relative;
      padding-bottom: 35px;
      &:before {
        content: '';
        position: absolute;
        border-top:  $border;
        border-left: $border;
        border-top-left-radius: 25px;
        height: calc(100% + 50px);
        top: .5em;
        width: 65px;
        right: calc(100% + 5px);
      }
    }

    &_left, &_right {
      position: relative;
      width: 100%;
      height: 100%;
      &:before {
        content: '';
        position: absolute;
        z-index: 1;
      }
    }

    &_left {
      &:before {
        border-bottom: $border;
        border-left: $border;
        border-bottom-left-radius: 20px;
        height: 40px;
        //bottom: 30%;
        top: to-unit(300px, em);
        width: calc(100% + 20px);
        left: -3px;
      }
    }

    &_right {
      &:before {
        border-top: $border;
        border-right: $border;
        border-top-right-radius: 10px;
        height: 40px;
        //top: 30%;
        bottom: to-unit(210px, em);
        width: calc(100% + 40px);
        right: -3px;
      }
    }
  }

  &__position_middle {
    width: 100%;
    //background-color: grey;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    overflow: hidden;
  }

  &__position_left, &__position_right {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 30px;
    position: relative;

    &:after {
      content: '';
      width: #{$z1};
      position: absolute;
      bottom: 20px;
      top: 20px;
      border-top: $border;
      border-bottom: $border;
    }

    --decentralized-side-padding: 130px;
    --decentralized-item-width: 245px;
    --decentralized-item-space: 30px;

    #{$d}__item {
      &:after {
        width: calc(100% - (var(--decentralized-item-width) + var(--decentralized-item-space)));
      }

      &:first-child, &:last-child {
        &:after {
          width: calc(100% - (var(--decentralized-item-width) + var(--decentralized-item-space) + #{$offset-radius}));
        }
      }
    }
  }

  &__position_left {
    &:after {
      border-right: $border;
      right: 0;
      border-top-right-radius: $z1;
      border-bottom-right-radius: $z1;
    }

    #{$d}__item {
      padding-right: var(--decentralized-side-padding);
      &:after {
        right: 0;
      }
      &:first-child, &:last-child {
        &:after {
          right: $offset-radius;
        }
      }
    }
  }

  &__position_right {
    &:after {
      border-left: $border;
      left: 0;
      border-top-left-radius: $z1;
      border-bottom-left-radius: $z1;
    }

    #{$d}__item {
      padding-left: var(--decentralized-side-padding);
      &:after {
        left: 0;
      }
      &:first-child, &:last-child {
        &:after {
          left: $offset-radius;
        }
      }
    }

    @media (max-width: 1024px) {
      margin-left: -2px;
    }
  }

  &__content {
    width: var(--decentralized-item-width);
    display: flex;
    align-items: center;
    position: relative;
    z-index: 1;
  }
}
</style>
