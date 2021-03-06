---
title: Frequently Asked Questions
description: Most common issues and how to fix them.
layout: page.html
---
## How it works

This is a living `common questions & answers` section.

Please ask your question on Stack Overflow: http://stackoverflow.com/questions/tagged/algolia+wordpress

If you are a developer, you can also open an issue on github at: https://github.com/algolia/algoliasearch-wordpress. We will regularly add the most frequently asked questions and answers found on Stack Overflow and Github about the Algolia Search plugin for WordPress, and append them to this very page.

If you are desperate and your deadline was yesterday, send us an email at [support+wordpress@algolia.com](mailto:support+wordpress@algolia.com).

**Please give priority to Stack Overflow and Github when asking for support, that way the whole community can benefit from it and you might get a faster answer. If you are having an issue, the chances are high other users might have the same. Let's share!**


## Questions & Answers

### Posts count are wrong on facets when using instantsearch.js

Currently we do not support displaying accurate counts in facets. This is due to the fact that we use the DISTINCT feature of Algolia to split posts into several small records.

### I was using the Beta version of your plugin, what exactly has changed?

Everything. Indeed we realized that the scope of our previous implementation was to large to be able to offer a good user experience.
We have since focused on the core features of this new plugin which allows to seamlessly synchronize any kind of content type you have with Algolia.
We also tried to be more close to the WordPress philosophy, allowing developers to easily extend this plugin so that it can be a good fit for any WordPress project.

We will definitely add features in the future, so if you are really missing something, feel free to suggest

### The previous Beta version of the plugin had some support for WooCommerce, what about this one?

As stated earlier, we narrowed down the scope of this plugin for now. That being said, we really want to offer a flexible way to use Algolia in your WooComerce website in the future.

If you are a developer and have built something based on this plugin, maybe we could work something out together fast enough!

### Can I customize the Autocomplete dropdown look & feel?

Yes. You can find some detailed explanations on [this page](customize-autocomplete.html).

### I have created a custom API key, but it is not accepted as Search-Only API key in the plugin settings.

Creating a dedicated search API key is indeed a good practice. If you want to be able to use that new generated API key as the Search-Only API key, you have to make sure it only has the `search` ACL privilege.
For security reasons, we reject every filled Search-Only API key that has additional privileges.

Secondly, we also require that the provided search API key has the TTL set to 0 (standing for unlimited validity in time). We do not want your users to get search outage.

### Will this plugin be compatible with my WordPress theme?

Yes. Actually this plugin introduces 2 main user oriented features:
- Native Search: Which overrides the default WordPress search with Algolia,
- Autocomplete: Which provides the user with an 'as you type' instant search experience.

In the first case, this plugin hooks into the WordPress native search feature. As a result, this will not impact your template because we only act on the backend side of things.

In the second case, we simply provide a dropdown menu that will be displayed underneath your search bar as you type. We have provided default scoped CSS rules so that the look and feel stays slick across different themes.

If you have any kind of issue related to default appearance, please send us a link to your website so that we can optimize our stylesheet.

### My data is out of sync with Algolia

Sometimes your WordPress content gets out of sync with Algolia. For example if you are changing your permalink templates, all your URLs will change and Algolia will not know about it.

Content also gets inconsistent when you use filters to change settings or attributes to push to Algolia.

In that case you can simply re-index your content.

### Can I use one Algolia account for multiple WordPress sites?

Definitely! In the same fashion that WordPress lets you prefix all database tables, we allow you to prefix every indices in Algolia.

This can be configured on the `Indexing` section of the plugin.

