<template>
  <Page>
    <ActionBar title="Welcome to WYWP" android:flat="true" />
    <TabView
      android:tabBackgroundColor="#53ba82"
      android:tabTextColor="#c4ffdf"
      android:selectedTabTextColor="#ffffff"
      androidSelectedTabHighlightColor="#ffffff"
    >
      <TabViewItem title="Home">
        <GridLayout columns="*" rows="*">
          <AddNewWifiPassword></AddNewWifiPassword>
        </GridLayout>
      </TabViewItem>
      <TabViewItem title="Tab 2">
        <GridLayout columns="*" rows="*">
          <Label class="message" text="Tab 2 Content" col="0" row="0" />
        </GridLayout>
      </TabViewItem>
      <TabViewItem title="Tab 3">
        <GridLayout columns="*" rows="*">
          <Label class="message" text="Tab 3 Content" col="0" row="0" />
        </GridLayout>
      </TabViewItem>
    </TabView>
  </Page>
</template>

<script >
import AddNewWifiPassword from "./AddNew";
export default {
  data() {
    return {
      msg: "Hello World!"
    };
  },
  components: { AddNewWifiPassword }
};
</script>

<style scoped>
ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}
</style>
