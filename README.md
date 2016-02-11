## About This Project

In the near future, numerous FAA applications are going to be migrating to the cloud. Different stakeholders from dev, ops, contracts, the cloud program management office, and FAA lines of business have different views about why, when, and how this should happen.

One way to better achieve convergence of views and alignment of interests is by publicizing a core FAA Cloud Services playbook that offers tiers of modernization to allow application owners and IT shared services to collaboratively make a return-on-investment based decision for individual apps as part of their cloud transformation.

## We Want Your Feedback
We encourage your feedback and suggestions on these documents. Content and feature suggestions and discussions are welcome via GitHub. Alternatively, please [e-mail Sean McBride](mailto:Sean.McBride@faa.gov).

## Technical Details

The FCS Playbook are compiled from [Markdown](https://help.github.com/articles/github-flavored-markdown "Link to More Information About Markdown") files using [Jekyll](https://github.com/jekyll/jekyll "Link to More Information about Jekyll"). The Plays from the Playbook are [available in the `_plays` folder](https://github.com/WhiteHouse/playbook/tree/gh-pages/_plays "Link to the Plays Markdown files"), 

You can also use Github's in-browser editing feature to make an edit to one of these Markdown files and submit your change for consideration without needing to install any additional software.

### Running the Site Locally

To run the site locally on your own computer (most helpful for previewing your own changes), you will need to install Jekyll and other dependencies:

If you don't already have Ruby and Bundler installed, follow [the first two steps in these Jekyll installation instructions](https://help.github.com/articles/using-jekyll-with-pages#installing-jekyll "Installation instructions for Jekyll").

Next, [fork this repository](http://help.github.com/fork-a-repo/ "Instructions for Forking Your Repository") and clone it on your computer.

Navigate to the folder on your computer, and run the command `$ bundle install` at the command line prompt.

To run the site locally, run `jekyll serve --watch`, then visit `http://localhost:4000/` in your browser to preview the site.

### Editing the Stylesheets

This project uses [Sass](http://sass-lang.com/ "Link to Learn More About Sass") for managing its style sheets. These styles are defined in the [`styles.scss` file](assets/_sass/styles.scss). We use [Jekyll's native SASS support](http://jekyllrb.com/docs/assets/) to auto-generates the required CSS when you run the site locally, as described above.

## License
As a work of the United States Government, this project is in the public domain within the United States.

Additionally, we waive copyright and related rights in the work worldwide through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
