# supermarket-prefixes

View the [list of prefixes](prefixes.yml) in YAML format.

## Why namespaces?

Chef Supermarket is a great place to share cookbooks, but it's rare to find a cookbook that will meet everybody's needs. Cookbooks are often forked, but you can't share your improvements on Supermarket using the original name.

As a GitHub user, you're already familiar with namespaces. When you fork a repository, you make a copy under your own username without actually renaming the repository itself. Unfortunately, Chef Supermarket lacks support for this kind of true namespace. Instead, we can approximate the idea of namespaces by using prefixes on our cookbook names.

Namespaces are about administrative boundaries, and are usually a reflection of who has the ability to make changes to the repository. Namespaces are granted to both people and organizations.

As the use of namespace prefixes grows there will be an increasing chance of accidental collisions, or conflict over desirable names. Hence the importance of [having a registry](https://www.iana.org/assignments/enterprise-numbers/enterprise-numbers). Chef Supermarket already serves as a registry of cookbook names, but has no support for registering or using namespaces. And that's why this registry exists.

And even if you're not using Supermarket, you should still be namespacing your cookbooks. If you implement a great `nginx` cookbook, for example, but somebody is already depending on the original `nginx` cookbook, they can't start using yours because there is a naming conflict. Using namespaces supports adoption and migration to new cookbooks.

## Claim your namespace

1. Upload a cookbook to [Chef Supermarket](https://supermarket.chef.io/). The `name` attribute in cookbook metadata must include your namespace as a prefix.
2. Submit a pull request to this repository.

## Rules

1. You cannot claim a namespace until you've uploaded a cookbook to [Chef Supermarket](https://supermarket.chef.io/). The cookbook must be more than a placeholder, and cannot consist entirely of boilerplate.
2. Product and technology namespaces cannot be claimed. For example, you cannot claim "memcached" as your namespace.

## Naming guidelines

Your cookbook repository in GitHub should use the same name that is specified in your cookbook metadata. <!-- This facilitates searching for cookbooks in GitHub. --> Use the description to identify it as a cookbook.

Some groups choose to create a new GitHub organization to collect their cookbook repositories into a single place. These organizations are commonly named "#{organization}-cookbooks".

If you don't have a separate organization but you still want to give your repository a name which clearly indicates that it is a cookbook, the preferred style is to add `cookbook-` as a prefix to the repository name.

Avoid using the words "chef" or "cookbook" when specifying the cookbook name in metadata.rb.
