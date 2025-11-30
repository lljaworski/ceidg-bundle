# CEIDG Bundle

Symfony bundle for integrating with CEIDG (Centralna Ewidencja i Informacja o Działalności Gospodarczej) - the Polish Central Register and Information on Business.

## Overview

This bundle provides a foundation for integrating CEIDG API services into your Symfony 7.3+ application with API Platform 4.2 support.

## Requirements

- PHP 8.2 or higher
- Symfony 7.0 or higher
- Symfony HTTP Client component

## Installation

### Step 1: Install via Composer

```bash
composer require lljaworski/ceidg-bundle
```

### Step 2: Enable the Bundle

If you're not using Symfony Flex, add the bundle to `config/bundles.php`:

```php
return [
    // ...
    LukaszJaworski\CeidgBundle\CeidgBundle::class => ['all' => true],
];
```

### Step 3: Configure the Bundle

Create a configuration file `config/packages/ceidg.yaml`:

```yaml
ceidg:
    api_url: '%env(CEIDG_API_URL)%'
    api_key: '%env(CEIDG_API_KEY)%'
```

### Step 4: Set Environment Variables

Add the following to your `.env` file:

```bash
CEIDG_API_URL=https://dane.biznes.gov.pl/api/ceidg/v2
CEIDG_API_KEY=your_api_key_here
```

You can obtain your CEIDG API key from [https://dane.biznes.gov.pl/](https://dane.biznes.gov.pl/).

## Configuration

Default configuration:

```yaml
ceidg:
    api_url: 'https://dane.biznes.gov.pl/api/ceidg/v2'  # Default CEIDG API URL
    api_key: ''  # Required: Your CEIDG API key
```

## Structure

```
ceidg-bundle/
├── src/
│   ├── CeidgBundle.php              # Main bundle class
│   ├── DependencyInjection/         # Symfony DI configuration
│   ├── Service/                     # Business logic services
│   ├── Command/                     # Console commands
│   ├── Entity/                      # Doctrine entities
│   ├── Repository/                  # Database repositories
│   ├── ApiResource/                 # API Platform resources
│   └── State/                       # API Platform state providers/processors
├── config/
│   └── services.yaml                # Service definitions
├── tests/
│   ├── Unit/                        # Unit tests
│   └── Functional/                  # Functional tests
├── composer.json
└── README.md
```

## Development

### Running Tests

```bash
cd ceidg-bundle
vendor/bin/phpunit
```

### Adding Services

Place your services in `src/Service/` directory. They will be automatically registered and available for autowiring.

### Adding Commands

Create console commands in `src/Command/` directory. They will be automatically tagged as console commands.

### Adding API Resources

Create API Platform resources in `src/ApiResource/` directory with corresponding state providers/processors in `src/State/`.

## Architecture

This bundle follows:
## Links

- [Packagist](https://packagist.org/packages/lljaworski/ceidg-bundle)
- [GitHub Repository](https://github.com/lljaworski/ceidg-bundle)

## License`composer.json` with proper repository information
3. Set up CI/CD for independent testing
4. Publish to Packagist
5. Update main project to use the package via Composer

## License

MIT

## Authors

- Lukasz Jaworski

## Contributing

Contributions are welcome! Please submit pull requests with tests and documentation.

## Support

For issues and questions, please use the GitHub issue tracker.
