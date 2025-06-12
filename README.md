# JOGI WhatsApp Messenger

A professional WhatsApp bulk messaging tool built with React, TypeScript, and Supabase.

## Features

- **WhatsApp Business API Integration**: Send messages directly through WhatsApp
- **Bulk Messaging**: Send messages to multiple contacts at once
- **Media Support**: Send images, videos, PDFs, and documents
- **Contact Management**: Add, edit, and organize your contacts
- **Real-time Status Tracking**: Monitor message delivery status
- **Analytics Dashboard**: View messaging statistics and performance
- **Responsive Design**: Works on desktop and mobile devices

## Setup Instructions

### 1. WhatsApp Business API Setup

To use this tool, you need to set up WhatsApp Business API:

1. **Create a Facebook Developer Account**
   - Go to [Facebook Developers](https://developers.facebook.com/)
   - Create a new app and select "Business" as the app type

2. **Add WhatsApp Business API**
   - In your Facebook app, add the WhatsApp Business API product
   - Follow the setup wizard to configure your business account

3. **Get Your Credentials**
   - Access Token: From your app's WhatsApp > API Setup page
   - Phone Number ID: The ID of your WhatsApp Business phone number
   - Business Account ID: Your WhatsApp Business Account ID
   - Webhook Verify Token: Create a secure token for webhook verification

4. **Configure Webhooks**
   - Set your webhook URL to: `https://your-domain.com/functions/v1/whatsapp-webhook`
   - Use your verify token for webhook verification
   - Subscribe to `messages` events

### 2. Environment Variables

Create a `.env` file with the following variables:

```env
# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# WhatsApp Business API Configuration (for Edge Functions)
WHATSAPP_ACCESS_TOKEN=your_whatsapp_access_token
WHATSAPP_PHONE_NUMBER_ID=your_phone_number_id
WHATSAPP_BUSINESS_ACCOUNT_ID=your_business_account_id
WHATSAPP_WEBHOOK_VERIFY_TOKEN=your_webhook_verify_token
```

### 3. Database Setup

The application uses Supabase for data storage. The database schema includes:

- **contacts**: Store contact information and message status
- **messages**: Track sent messages and delivery statistics
- **message_attachments**: Handle file attachments

### 4. Deployment

The application can be deployed to Netlify or any static hosting service. Make sure to:

1. Set up your environment variables in your hosting platform
2. Deploy the Supabase Edge Functions for WhatsApp integration
3. Configure your WhatsApp webhook URL to point to your deployed functions

## Usage

1. **Setup WhatsApp**: Complete the WhatsApp Business API setup when first launching the app
2. **Add Contacts**: Use the Contact Manager to add individual contacts or bulk import
3. **Compose Messages**: Create your message with optional media attachments
4. **Send Messages**: Send to all contacts with real-time status tracking
5. **Monitor Results**: View delivery statistics in the Dashboard

## Important Notes

- **WhatsApp Policies**: Ensure compliance with WhatsApp's messaging policies
- **Rate Limits**: WhatsApp has rate limits for message sending
- **Testing**: Test with a small number of contacts first
- **Security**: Keep your API credentials secure and never expose them publicly

## Support

For WhatsApp Business API documentation and support:
- [WhatsApp Business API Documentation](https://developers.facebook.com/docs/whatsapp)
- [WhatsApp Business Policy](https://www.whatsapp.com/legal/business-policy)

## License

This project is for educational and business use. Ensure compliance with WhatsApp's terms of service.