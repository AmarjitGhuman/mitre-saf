<template>
  <v-content>
    <div class="title text-justify pa-2">
      <p>
        These open-source community-based InSpec profiles validate the security of
        common system components. MITRE is helping to provide stewardship over
        these profiles, hosted here and at other community vendor sites. If you
        are interested in new profiles, please contact us at
        <a
          :href="mail_link"
        >{{ db.CommunityEmail }}</a>. If you are interested in developing and contributing your own
        profiles, please see our links to Training material.
      </p>
    </div>
    <profileTemplate :profiles="baselines" />
  </v-content>
</template>

<script>
import profileTemplate from "@/components/profiles/profileTemplate.vue";
import baselines from "@/assets/data/baselines.json";
import db from "@/assets/data/communitydata.json";

export default {
  components: {
    profileTemplate
  },
  data() {
    return {
      baselines: baselines,
      db: db
    };
  },
  computed: {
    mail_link() {
      return "mailto:" + db.CommunityEmail;
    }
  }
};
</script>

<style scoped>
p {
  text-align: left;
  padding: 5px 0;
}
.break-word {
  overflow-wrap: normal;
  word-wrap: break-word;
  word-break: normal;
  hyphens: auto;
}
</style>