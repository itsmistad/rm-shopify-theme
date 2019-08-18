<div align="center">
    <a href="https://redmarkdeals.com" target="_blank"><img class="redmark__logo" src="https://cdn.redmarkdeals.com/redmark_logo-full.png" alt="RedMark Logo"/></a>
    <p>A premium Shopify theme with built-in apps <s>made by a monkey</s></p>
</div>

___

#### Features

1. Sleek header with a responsive logo, cart preview, and mobile-friendly behavior.
2. Consistent typography throughout the theme.
3. Multiple newsletter implementations with MailChimp integration.
4. Trust badges, social media buttons, and payment provider badges embedded into the footer.
5. Multiple useful home page sections.
6. Pre-code-configured for essential apps that are already picked out for you. 
7. A GDPR-compliant cookie bar and a customizable announcement bar.
8. Virus- and gluten-free.

## Shopify Theme Kit

This branch runs on the [Shopify Theme Kit](https://shopify.github.io/themekit/).
This branch also requires [bash](https://git-scm.com/downloads), [node](https://nodejs.org/en/download/), and [choco](https://chocolatey.org/install) to function, so make sure to have those installed.

It is highly recommended you use this in conjunction with a [Shopify Partners](https://www.shopify.com/partners) store so that you can develop on an environment that is isolated from your live store.

To take full advantage of this theme, use the same plugins as found on [this spreadsheet](https://docs.google.com/spreadsheets/d/1uH1LK3mLPdQDSeOetnEQVv41eN-27GgdUSVzP5lXges/edit?usp=sharing).

### Installation
#### Installing the Shopify Theme Kit
> choco install themekit

Pretty simple.

### Configuration
In order to connect the kit to your shopify store(s), you need to modify your `config.yml`. An example file (`example.config.yml`) has been provided to show you the structure.

Use your real store for your `prod` credentials and your partner store for your `dev` credentials.

#### Retrieving the Theme ID
> theme get --list -p=(your-password) -s=(your-store.myshopify.com)

This ID is required for your configuration. The password here is the password generated by the private managed app you must create in your store's admin page. To do this, go to your `Apps` view and click the small linked text at the bottom.

### Usage

Before running any bash command, ensure that you are in `./scripts/`.
Valid options for `environment`:
- `prod`
- `dev`

#### Pull from Environment
> ./get.sh `environment`

This will switch your `settings_data.json` to your target environment's and download your theme from the Shopify cloud.

#### Swapping Environments
> ./swap.sh -f `environment`

This will switch your `settings_data.json` to your target environment's and keep the code you currently have locally.

#### Start Live Preview
> ./start.sh

This will watch and actively deploy any changes to your local source files. The deployment target is your currently mirrored environment.

#### Deploy to Environment
> ./deploy.sh

This will build and deploy your local source files to your currently mirrored environment. This is *not* necessary when in live preview.
