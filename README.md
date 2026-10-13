# Shoploc Loyalty Service

## Overview

`shoploc-loyalty-service` is a backend microservice responsible for managing
the loyalty program of the Shoploc platform.

It manages customer loyalty points, loyalty status, rewards, and benefits
associated with customer activity and purchases.

The service is part of the Shoploc microservices architecture.

## Responsibilities

The Loyalty Service is responsible for:

- Managing customer loyalty accounts
- Managing loyalty points
- Adding and removing loyalty points
- Calculating points earned from eligible purchases
- Managing customer loyalty status
- Managing rewards and benefits
- Managing loyalty-related business rules
- Providing loyalty APIs to clients and other Shoploc services
- Processing loyalty events related to customer purchases

The Loyalty Service contains loyalty-related business logic.

Order management remains the responsibility of
`shoploc-order-service`.

Payment processing remains the responsibility of
`shoploc-payment-service`.

Authentication and identity management remain the responsibility of
`shoploc-identity-service`.

## Architecture

```text
                         Clients
                            │
                            ▼
                  ┌─────────────────────┐
                  │   Shoploc API       │
                  │      Gateway        │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │   Loyalty Service   │
                  │                     │
                  │ Loyalty Accounts    │
                  │ Points              │
                  │ Status              │
                  │ Rewards             │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │    Loyalty DB       │
                  └─────────────────────┘