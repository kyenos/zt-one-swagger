
#Zero Tier One API swagger descriptor

Included in this repository is a swagger descriptor for the ZeroTier One API. This is a third party definition file that
attempts to abstractly define the service based on available documentation any individual experimentation with ZeroTier.

ZeroTier is a global, secure network, and for those of you whom are unfamiliar with it, I strongly encourage you to check
out the project at; https://zerotier.com

The descriptor is stored as a YAML (https://yaml.org/spec/) file in Swagger 2.0 (http://swagger.io)

The license choice of Apache 2.0 was made with intent match ZeroTier's choice in open source licensing, hopefully as
close as possible.

*Note;* that from the authors point of view, the work put into the contents of this repository are public domain. On 
the other hand, there are elements here that represent the innovation, creation, copyright, intellectual property and
trademark of third parties. While every effort has been made by the author to ensure compliance with licensing and fair
use trademark, those items that are not directly the invention, work or concept of the author *still* belong to those 
entities. 

It is expressly *not* the responsibility of the author but solely the responsibility of the user should *any* use or 
derivative use of this project by any individual or entity constitute a breach, grievance or conflict with the 
licensing, EULA, usage and or rights of ZeroTier or any other appropriate stake holder. That means be sure that the
way you plan to use this work is appropriate.

This project is published solely in the hopes that it will prove useful and save time for someone else.

## What is an API swagger descriptor?
This is kind of a loaded question. It is an abstract definition of a RESTful (https://restfulapi.net/) service. ZeroTier
exposes they SaaS offering 'ZeroTier One' as an API available for developers to access and control their individual
networks and member nodes. This project describes that API in a standard form conforming to the Swagger 2.0 specification.

The resulting definition file presented here is both human readable, and machine consumable. This allows the individual
to gleam lots of advantages and several different avenues of action moving forward:
- It can be seen as documentation that is clear, concise and readable by a human
- It can be consumed by a tool to either take further action or to for translation to another form

In the latter case, all kinds of opportunity arise, here are some samples:
 - Creating static client libraries in different languages
 - Creating mock services to test code against so you can develop without needing access to or impacting performance
   of the real service
 - Creating documentation
 - Re-implementation of a service in a new language while maintaining comparability with existing clients
 - Dynamically adjust client code when contract changes occur since they will be published in a standard form
 
If you're interested in knowing more about how tooling can accomplish these and other tasks, a great place to start at
is [swagger-codegen](https://swagger.io/tools/swagger-codegen/download/). If noting else you will discover how to create
code based off this file in as many as 35 different language / framework combinations. 

Even better, plop the definition into the [swagger editor online](http://editor.swagger.io/), click 'Generate Client' then
select bash. This will download a command line bash script that can be sued to interact with ZeroTier One... no coding
necessary.

## What it is not
This project is not code, it is not an implementation of anything ZeroTier. You must take further action in order to use
it in any particular way other than simply reading it as a human. The author doesn't guarantee that it's an exact match
as it is manually created and maintained. 

## Why
This project is not affiliated with ZeroTier in any wa, other than that I needed a way to actually use their client API.
As such there are no guarantees that they will or will not make breaking changes to the service which in turn invalidate
the contract presented here.

It is actually the very reason I started this, as the MSON (A specification similar to swagger which can be found [here](https://github.com/apiaryio/mson/blob/master/MSON%20Specification.md))
file that originally was used to publish their API documentation (https://my.zerotier.com/static/central-api.md) is no 
longer valid (gives a 404). I did manage to find a copy out there that unfortunately was painfully out of date. Manually
making curl calls in a script, didn't appeal to me either as it's very difficult to maintain and debug.

My other option was an open source [ZeroTier SDK](https://github.com/sbilly/ZeroTierSDK) which seemed overkill for my 
purposes... not to mention I didn't really want to write a full blown c++ application / project just to get some cli / 
bash scripting accomplished... specifically list member nodes and their descriptions.

I pondered over whether to publish this or not, but in the end decided that if it would help anyone else avoid the 3 
days of pulling my hair out, it would be worth it. Anyone who's worked with REST API's before will be able to tell you
that when there's not just good documentation but, a good service description file, the API is a breeze, but when you
have to write you're own client code, it's an exercise in frustration.