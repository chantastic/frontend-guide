# Frontend Guide
A Guide to PCO Frontend Tools and Techniques

1. [Interfaces](#interfaces)
1. [InterfacesIcons](#interfacesicons)
1. [minions.css](#minionscss)
1. [Rails SJR](#rails-sjr)
1. [Turbolinks](#turbolinks)

## Interfaces
> Interfaces is a small collection of UI elements shared between all PCO apps. Consider it a starting point, not an absolute solution.

### Things you should know:

#### The Topbar lives in Interfaces
Topbar is one of the few responsibilities of Interfaces. All the smarts about app and user switching happens in Interfaces.

#### Interfaces is a starting point
Don't feel weird about "outgrowing" Interfaces. It's a starting point. In versions to come, improving extensibility is the foremost concern.

#### UI doesn't get developed in Interfaces
Developing in a shared/versioned/changelogged space is painful. Avoid the pain by developing and testing new UI app-side. After it's proven to be useful and stable, PR it into Interfaces.

### References
* Docs: [http://pco-interfaces.herokuapp.com](http://pco-interfaces.herokuapp.com/interfaces)  
* Repo: [https://github.com/ministrycentered/interfaces](https://github.com/ministrycentered/interfaces)

## InterfacesIcons
> InterfacesIcons provides shared icons to PCO apps. SVG icons are made available in Rails and React variants.

### Things you should know:

#### Not all apps are on it yet
At the time of writing only People and Check-Ins use InterfacesIcons. And Check-Ins is on an old pre-SVG version.

#### It's a WIP
If you find parts of it painful, let [me](@chantistic) know.

#### Eventually all icons will live here
SVGs are more accessible than icon-fonts. Once we've worked out the kinks, this will be the single repository for Planning Center icons.

### References
* Available Icons: [http://pco-interfaces.herokuapp.com/interfaces_icons](http://pco-interfaces.herokuapp.com/interfaces_icons)  
* Repo/Docs: [https://github.com/ministrycentered/interfaces_icons](https://github.com/ministrycentered/interfaces_icons)

## minions.css
> Minions are a large collection of responsive-capable utility classes. They serve to eliminate the proliferation of BEM modifiers and necessary nudges. It's literally so much jargon, who knows what it means?

### Things you should know:

#### Load order matters
minions classes need to be **last** in your CSS manifest. They only have a specificity of `0,0,1,0`. So, write your styles carefully.

#### Utility classes are a great alternative to "modifiers"
If you've used BEM for a while, you know modifiers are where the entire system gets crufty. Reach for minions before creating new modifiers.

#### Best-practices are TBD
Utility classes are a relatively new addition to our frontend toolset. So, it's possible to over use them. Know that we don't have any tools yet to provide data about commonly used collections of used utility-classes.

### Resources
* minions.css (source): [https://github.com/chantastic/minions.css](https://github.com/chantastic/minions.css)  
* minions_rails (Rails asset gem): [https://github.com/chantastic/minions_rails](https://github.com/chantastic/minions_rails)  

## Rails SJR
> Server-generated JavaScript Responses are a technique we make heavy use of in our Rails apps. It should be the first-line of defense in adding interactivity to a Rails page.

### Resources

* Example: [https://signalvnoise.com/posts/3697-server-generated-javascript-responses](https://signalvnoise.com/posts/3697-server-generated-javascript-responses)

### react-rails

* Repo: [https://github.com/reactjs/react-rails](https://github.com/reactjs/react-rails)

## Turbolinks
> Turbolinks makes following links in your web application faster. Instead of forcing the browser to recompile the JavaScript and CSS between each page, it keeps the current page instance alive and replaces only the body (or parts of) and the title in the head.

### Things you should know:

#### We use 2 versions of Turbolinks
* [Turbolinks Classic](https://github.com/turbolinks/turbolinks-classic) is used in most of our apps.
* [Turbolinks (v5)](https://github.com/turbolinks/turbolinks) is used in apps that have been migrated to Rails 5 (or are in that process).

Make sure you're viewing documentation for the Turbolinks version loaded in your app. These versions are **very** different.

#### Turbolinks affects jQuery and React
* [Running jQuery initializer functions in **Turbolinks Classic**](https://github.com/turbolinks/turbolinks#running-javascript-when-a-page-loads)
* [Running jQuery initializer functions in **Turbolinks v5**](https://github.com/turbolinks/turbolinks#running-javascript-when-a-page-loads)
* [Mounting/unmounting React Components using the `react_component` helper](https://github.com/reactjs/react-rails#rendering--mounting)

### References
* Turbolinks Classic: [https://github.com/turbolinks/turbolinks-classic](https://github.com/turbolinks/turbolinks-classic)
* Turbolinks (v5+): [https://github.com/turbolinks/turbolinks](https://github.com/turbolinks/turbolinks)
