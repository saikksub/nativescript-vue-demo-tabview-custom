<template>
    <Page
        actionBarHidden="false">
        <ActionBar
            title="Custom TabView Demo"
            flat>
        </ActionBar>
        <GridLayout
            rows="*,60">
            <StackLayout row="0" orientation="vertical">
                <GridLayout columns="*" rows="*">
                    <Label :text="msg" col="0" row="0" style="text-align: center;"/>
                </GridLayout>
            </StackLayout>
            <FlexboxLayout row="1" alignItems="center" justifyContent="space-between" class="bottom-navigation">
                <StackLayout
                    v-for="(item, index) in nav"
                    :key="index"
                    class="hero-view"
                    width="80"
                    orientation="vertical"
                    @tap="onTapTab(item)">
                    <Label
                        :text="`${(item.icon )}` | fonticon"
                        class="fa icon" />
                    <Label
                        :text="item.title"
                        class="nav-label" />
                </StackLayout>
            </FlexboxLayout>
        </GridLayout>
    </Page>

</template>

<script>
  export default {
    data() {
      return {
        msg: 'Home',
        nav: [
          { title: 'Home', icon: 'fa-home' },
          { title: 'List', icon: 'fa-list' },
          { title: 'Cards', icon: 'fa-id-card' },
          { title: 'Settings', icon: 'fa-cog' }
        ]
      }
    },
    methods: {
      onTapTab: function ({ title }) {
        this.msg = title
      }
    }
  }
</script>

<style scoped>
    ActionBar {
        background-color: #53ba82;
        color: #ffffff;
    }
    .hero-view {
      vertical-align: center;
      text-align: center;
      font-size: 25;
      color: #333333;
    }
    .nav-label {
      font-size: 14;
    }
    .bottom-navigation {
      background: rgb(225, 229, 236);
    }
</style>
