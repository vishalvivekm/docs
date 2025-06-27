---
draft: false
---

---
docType: "Chapter"
id: "deploy-dapr-statestore-component.mdx"
chapterTitle: "Deploy Dapr StateStore Component"
description: 
videos: 0
lectures: 4
order: 4
---
<ChapterStyle>
<h3 class="chapter-sub-heading">Create, Configure and Deploy Dapr Redis State Store Component</h3>

Following the deployment of the Redis state store, we will use Meshery to create and configure the Dapr state store component. This involves specifying essential details, including the redisHost and redisPassword fields in the Dapr component configuration, which tell Dapr where to find the Redis server and how to authenticate.

This setup ensures that Dapr connects to the correct Redis instance, allowing it to handle state management seamlessly without direct involvement from your application.

<h4 class="chapter-sub-heading">Search for Component</h4>

1. On the Dock at the bottom of the design canvas, click on **Components**.
1. Search for "dapr".
1. Click on the drop-down and drag and drop **component** to the design canvas. This is the Dapr component custom resource we discussed when learning about the Dapr control plane.

<CustomImage
  src={"/images/learning-path/dapr/drag-component.png"}
  align="center"
  width="100%"
/>
<h4 class="chapter-sub-heading">Configure State Store and Deploy</h4>

Now you can start configuring the Dapr state-store.

1. Click on the component to open the configuration tab.
1. Enter _state-store_ as the **name**.
1. Enter _kubernetes_ in the **Secret store** field.
1. Enter _state.redis_ in the **Type** field.
1. Enter _v1_ in the **version** field.

<CustomImage
  src={"/images/learning-path/dapr/state-store.png"}
  align="center"
  width="100%"
/>

<MesheryDesignEmbed
  embedId="embedded-design-f0b9088c-ab17-41ee-9400-fcfc5f4d59a8"
  embedScriptSrc="/images/learning-path/embed-test/embedded-design-statestore.js"
/>

1. Click on the **metadata** drop-down and begin to fill in the info.
1. For **Name**, enter _redisHost_.
1. For **Value**, enter _redis-master.default.svc.cluster.local:6379_.
1. Under **Secret Key Ref**, enter the pair _redis:redis-password_.

<CustomImage
  src={"/images/learning-path/dapr/metadata.png"}
  align="center"
  width="100%"
/>
5. Click the **Actions** button and deploy.

Next we will deploy the Python and Node.js applications.

</ChapterStyle>
