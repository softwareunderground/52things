# Software Challenges in Oil and Gas

Bill Menger

## The Need

Geoscientists demand specialized “best of breed” software applications.  This has resulted in a proliferation of commercial software usage in oil and gas companies. While effective, the use of commercial software holds inherent strategic challenges.
 

## Software Challenges

Software is an expensive but vital component of a successful oil and gas company’s E&P strategy. Due to the high cost of development and maintenance, organizations usually find it more cost-effective to purchase software than to develop it in-house.
When buying commercial software, each company must address the following challenges:

- How to sustain a competitive advantage if you use the same software as your competitors
- How to incorporate a needed new feature that the commercial applications do not support
- How to ensure that different data formats can be read by multiple applications.

Even when commercial software comprises the bulk of applications used in a company, researchers still need to create new programs.  If the expertise to produce and deploy proprietary software is missing, how does technology transfer from the research and development function to the operating units?
 

## Extending Commercial Software

Extending commercial software with a Software Development Kit (SDK) offers one approach to resolving the challenges.  Many commercial applications have carved out a niche in a particular geoscience specialty such as seismic processing or petrophysics. However, SDKs do have some drawbacks.

- Applications are often built using different software languages.
- Applications run on different operating systems.
- Licensing an application just to leverage its SDK can be expensive.
- Some SDKs are designed for use by professional developers and not by geoscientists.
- Adding new functionality into an existing application can be difficult.
- Software reuse among different SDKs is often impossible.
- Data exchange can be a problem.

Using a commercial SDK makes sense for some types of problems. For instance, in the case of a seismic processing system, the problem can be expressed generically as the task of applying a sequence of operations to a collection of seismic traces on a cluster of machines. If you are building a seismic processing module, then the odds are excellent that you can leverage a lot of the functionality in an SDK.

Many SDKs support plug-in extensions to a limited degree, but this does not mean that the application will be sufficiently extensible to support all needs. For example, multi-component seismic data is not supported in most of the current SDKs. One would have to add input/output functionality, visualization code and new data structures to handle multi-component data before effectively adding such new functionality to the software.

Data exchange issues are exacerbated by each SDK’s use of a different database.  Middleware technology (e.g. OpenSpirit, GeoShare) and workarounds involving file transfers can be employed in many cases, but sometimes developers must extend several applications with custom input and output code in order to complete a workflow for production use.
 

## Developing Software Internally

In an era where the same software is used by most companies, it is tempting to try to gain a competitive advantage by developing more software in-house. However, the requirements for in-house software are just as demanding as those for commercial software, and development is handicapped by fewer resources and a relatively small user base that provides limited feedback.

Based on historical project data, internally developed software has a lifetime cost of approximately $100 for each line of code that is written.  This shows a clear need to avoid writing code whenever possible.  The easiest way to do this is to employ a “buy-versus-build” strategy and to focus on building only the most valuable new functionality.

Software developed internally needs to have a high perceived business value. This is achieved by building new functionality that cannot be purchased commercially, which occurs when the functionality is innovative or when it is a niche application with a small user base.

Oil companies frequently generate software requirements that are specific to business processes and the geological provinces being explored.  Commercial vendors cannot expect a reasonable return on investment if they tailor software to fit such specific business needs and so it is left to the oil and gas company to build its own software… or is it?
 

## Open Source Strategy

The following quote is from the authors of Innovation Happens Elsewhere, Open Source as Business Strategy by Ron Goldman and Richard P. Gabriel (Morgan Kaufmann Publishers, San Francisco).

> …companies need to find ways to use outside innovations and to become part of a distributed fabric of innovation through a combination of licensing and well chosen gifts. Although the concept of a gift may not at first seem to fit well with free-market capitalism, it might when thought of in the context of collaborating with others to build common commodity-like infrastructure.

If the oil and gas company could make effective use of open source software, and give back to the open source project from time to time, then it could find itself with lower total cost of ownership, higher usability in its internal codes, and research software that finds solid usefulness in its operating units.  The goal of using an open source project is to avoid spending time writing code that others have already written – code that does the basic I/O, visualization, menu-ing, graphical user interface design, etc. and to concentrate on the software that gets the geophysics done.
 

## Sustainable Open Source Development

Sustainable open source development requires a stable entity that can house the software, maintain the web presence, advertise and solicit for collaboration, and to own the intellectual property. The ideal entity is a non profit organization whose purpose is to foster collaboration and elevate the common good. It should have as one goal the education of the next generation of geoscientists.

Sustainable open source development also requires proper licensing that allows:

- businesses to use the product to make money,
- universities to use the product to house research projects and to train students,
- oil and gas companies to use the product to house proprietary programs.
 
In order for this kind of product development to be successful in the geophysical realm, it will need to:

- support multiple data formats,
- contain a standardized domain model,
- simplify development of new data visualization tools,
- encourage code reuse,
- have a user-friendly design,
- have the potential to evolve as a geoscience development platform,
- be built upon a solid foundation and framework.
 

## Managing Open Source Software

Software is available.  For seismic processing, there are Madagascar, SU, CPSeis, and FreeUSP.  For quantitative interpretation there is QI and for general purpose interpretation utilities there is GeoCraft.  What we lack on some of these projects is the proper open-source license. We also lack the non-profit organization that can bring geophysical open-source projects into an umbrella legal structure and merge the frameworks where appropriate.  We need the organization that can relicense with business-friendly licensing that helps the developers to justifiably reap some rewards for their efforts but that still allows the hobbyist and student to use the software.
 

## Parting Thoughts

As a founding member of the GeoCraft team, I was able to think through many of these ideas, but the missing link then – and now – is the non-profit organization.  It is time to create that organization and to change the way the industry writes its software.  We should not want to damage the commercial software industry, but we do want to:

1. stop inefficient software development in the oil and gas companies,
2. create platforms for grad students to build their research upon, and
3. raise the bar for commercial offerings.
 
Pasted from <http://hpcinoilandgas.blogspot.com/2009/05/software-challenges-in-oil-and-gas.html> 
 