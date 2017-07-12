Style Guide
===========

=CSS=
Scoped or not?  Check bundled output for a v-for loop rendering multiple child components with both scoped and not scoped style tags.

=Components=
Use single file components and keep them small
Use JSDoc syntax at the top of every script component

=File Structure=
For components, mirror the natural view hierarchy, so a page is a folder, categories of child components are sub-folders, and so on.
For logic, such as models and data transformations, separate folders:
    * models
    * transformations
    * apis

=Project Plan=

* Finish current work for basic version
**(F) NEW: clicking on dashboard widget takes you to detail page without top nav area selected (I am pretty convinced we need to just globally use $store.getters.projectCode
**(M) Main logo should link to the dashboard
**(M) This bug is carried over from the prototype - we need to only highlight the area that we're in, so we have to de-highlight the Dashboard link, kind of tricky with the router
** Going back to the main screen sometimes shows 0 as the Total pageviews and doesn't display any data (I think when switching wikis and navigating a lot on the Detail page?

* Clean up any code that needs help
**(M) don't set $store.state directly - example: App.vue
**(M) area and metric getters don't make sense in the store, we already have them in the state
**(M) setProject doesn't make sense as an action, we can just setState or make a specific mutation
**(F) 4 tests are still failing - we can remove them if they're too hard to refactor but we should make sure they're not showing a mistake

* Nice to have
**(D) It would be nice to have a util function that returns something we can pass to router.push.  The signature could be util.getNewURL({ project, area, metric, options })
**(D) CSS variables


* Working time: 14:00 -> 17:00 CEST
* Schema: Metric configuration for UI
* Vertical Slice Decision: Active Editors, Pageviews, Unique Devices, Total Articles
* Schema: Metric query to the API
* URI Scheme for AQS, mock it return fake data for initial work?
* URI Scheme for front-end (how we make things bookmarkable)
* Decide how to implement the various widgets (like dashboard vs. detail ones, different visualizations, does it make sense together)
* Mechanical: implement all widgets
* Mechanical: reuse (by breaking up)? most of the dashboard and detail from prototype?
* Schema: Site configuration objects: personal preferences, saved wiki selection, etc., default site config, etc.
* Mechanical: CSS structure
* Internationalization: simple layer of abstraction on top of raw text


##Wikistats 2 Frontend

**To build the dev bundle and watch file changes**

```
npm run dev
```

**To run tests, watching file changes**

```
npm test
```

##Building

* Lodash customized to just what we need:

```
npm i -g lodash-cli
lodash include=assign,capitalize,debounce,filter,flatten,forEach,indexOf,kebabCase,last,take,transform
```
