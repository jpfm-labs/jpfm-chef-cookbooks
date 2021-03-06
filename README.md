# jpfm-chef-cookbooks
This is the main repo for the Chef-based configuration management automation code used at JPFM Labs. 

This automation code is built on the [attribute-driven-API cookbooks](https://github.com/facebook/chef-cookbooks) maintained by Facebook. This model for using configuration management is not the typical way people use configuration management tools like Ansible, Chef, Puppet, etc. Also, this model for using Chef is not the traditional way most people use Chef. It's worth reading this post on the [History of the Facebook Chef Cookbooks](https://engineering.fb.com/2016/04/15/core-data/facebook-chef-cookbooks/) and watching this [presentation](https://www.youtube.com/watch?v=-YtZiVxEiJ8) made by Phil Dibowitz when the code was open sourced. I've also created some [video training](https://www.oreilly.com/videos/learning-chef-for/9781491959442/) on the basics of this attribute-driven approach that is worth browsing, if you have an O'Reilly Media Subscription.

The goals for using infrastructure automation this way (refer to Phil's talks above for more detail):
- Can be supported by a very small infrastructure automation team
- Scales to ten of thousands of heterogeneous systems
- Permits self-service maintenance of any relevant settings for service owners that scales to even very large organizations
- Integrates nicely with any internal systems, even ones not maintained by the infrastructure automation team

The workflow involves:
- **Easy abstractions through "Configuration as Data"**. Configuration can be extended by anyone, anywhere by munging data structures
- **No need for systems knowledge**. Engineers don't need to know the details of what they're building on, just what they want to change
- **Change without fear**. Engineers can change their systems without fear of any unintended side-effects - the blast raidus is limited
- **Testing (in production)** Testing against real systems, safely, is useful and necessary, and easy
- **Idempotent systems**, not idemptent records, for easy rollback
