---
sidebar_position: 1
---

# Super Extension

## Functionality
1. Record/Execute walkthrough/automation skills.
2. Give skills suggestion in sidebar widget based on current active tab/page context.
3. Coordinate communication between Super API and Desktop Runtime through [Native Messaging Host](https://developer.chrome.com/docs/apps/nativeMessaging/).

```mdx-code-block
import DocCardList from '@theme/DocCardList';
import {useCurrentSidebarCategory} from '@docusaurus/theme-common';

<DocCardList items={useCurrentSidebarCategory().items}/>
```
