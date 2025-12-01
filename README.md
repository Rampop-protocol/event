# Event Ticketing Platform

A modern, full-featured event ticketing platform for creating, managing, and selling tickets to events online.

## Features

### For Event Organizers
- **Event Management** - Create and manage multiple events with detailed information
- **Ticket Types** - Configure multiple ticket tiers (General Admission, VIP, Early Bird, etc.)
- **Real-time Analytics** - Track sales, attendance, and revenue in real-time
- **Custom Branding** - Personalize event pages with logos, banners, and themes
- **Promo Codes** - Create discount codes and promotional campaigns
- **Attendee Management** - View and manage attendee lists, check-ins, and communications

### For Attendees
- **Easy Discovery** - Browse and search events by category, location, and date
- **Secure Checkout** - Fast and secure payment processing
- **Digital Tickets** - Receive tickets instantly via email with QR codes
- **Mobile-Friendly** - Fully responsive design works on all devices
- **Order History** - Access past purchases and upcoming events
- **Ticket Transfer** - Transfer tickets to friends seamlessly

### Technical Features
- **Payment Integration** - Support for Stripe, PayPal, and other payment gateways
- **Email Notifications** - Automated confirmations, reminders, and updates
- **QR Code Scanning** - Mobile app for fast check-ins at events
- **Seating Maps** - Interactive seat selection for venues
- **Waitlist Management** - Automatic notifications when tickets become available
- **Multi-language Support** - Localization for international events

## Tech Stack

- **Frontend** - React, TypeScript, Tailwind CSS
- **Backend** - Node.js, Express
- **Database** - PostgreSQL
- **Authentication** - JWT with refresh tokens
- **Payment Processing** - Stripe API
- **Email Service** - SendGrid
- **Cloud Storage** - AWS S3
- **Deployment** - Docker, Kubernetes

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL 14+
- npm or yarn
- Stripe account for payment processing

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/event-ticketing-platform.git
cd event-ticketing-platform

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Run database migrations
npm run migrate

# Start development server
npm run dev
```

### Environment Variables
```env
DATABASE_URL=postgresql://user:password@localhost:5432/ticketing
JWT_SECRET=your-secret-key
STRIPE_SECRET_KEY=sk_test_...
STRIPE_PUBLISHABLE_KEY=pk_test_...
SENDGRID_API_KEY=SG...
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
AWS_S3_BUCKET=your-bucket-name
```

## Usage

### Creating an Event
```javascript
POST /api/events
{
  "title": "Summer Music Festival 2025",
  "description": "The biggest music festival of the year",
  "date": "2025-07-15T18:00:00Z",
  "venue": "Central Park",
  "location": {
    "city": "New York",
    "country": "USA"
  },
  "tickets": [
    {
      "name": "General Admission",
      "price": 50,
      "quantity": 1000
    },
    {
      "name": "VIP",
      "price": 150,
      "quantity": 100
    }
  ]
}
```

### Purchasing Tickets
```javascript
POST /api/orders
{
  "eventId": "evt_123",
  "tickets": [
    {
      "ticketTypeId": "tkt_456",
      "quantity": 2
    }
  ],
  "paymentMethod": "stripe",
  "promoCode": "EARLYBIRD"
}
```

## API Documentation

Full API documentation is available at `/api/docs` when running the development server.

Key endpoints include:

- `GET /api/events` - List all events
- `GET /api/events/:id` - Get event details
- `POST /api/events` - Create new event
- `POST /api/orders` - Purchase tickets
- `GET /api/orders/:id` - Get order details
- `POST /api/check-in/:ticketId` - Check in attendee

## Testing
```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage

# Run e2e tests
npm run test:e2e
```

## Deployment

### Using Docker
```bash
# Build the image
docker build -t event-ticketing-platform .

# Run the container
docker run -p 3000:3000 --env-file .env event-ticketing-platform
```

### Using Docker Compose
```bash
docker-compose up -d
```

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and development process.

## Security

- All payments are processed securely through PCI-compliant payment gateways
- User passwords are hashed using bcrypt
- API endpoints are protected with JWT authentication
- Input validation and sanitization on all user inputs
- Rate limiting to prevent abuse
- Regular security audits and dependency updates

Report security vulnerabilities to security@example.com

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

- **Documentation** - [docs.example.com](https://docs.example.com)
- **Email** - support@example.com
- **Discord** - [Join our community](https://discord.gg/example)
- **GitHub Issues** - [Report bugs](https://github.com/yourusername/event-ticketing-platform/issues)

## Roadmap

- [ ] Mobile apps (iOS and Android)
- [ ] Blockchain-based ticket verification
- [ ] Live streaming integration
- [ ] Social media integration
- [ ] Advanced analytics dashboard
- [ ] Recurring events support
- [ ] Multi-currency support
- [ ] Affiliate program

## Acknowledgments

- Thanks to all contributors who have helped build this platform
- Inspired by leading ticketing platforms like Eventbrite and Ticketmaster
- Built with love for the events community

---

Made with ❤️ by the Event Ticketing Platform Team
