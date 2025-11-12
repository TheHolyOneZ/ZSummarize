# ZSummarize
ZSummarize is an advanced Discord bot that uses Google's Gemini AI to generate intelligent summaries of your server's chat history. Whether you need quick recaps of missed conversations or automated daily summaries, ZSummarize delivers professional, customizable results.

> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)

# ZSummarize

**AI-Powered Discord Channel Summarization System**

ZSummarize is an advanced Discord bot that uses Google's Gemini AI to generate intelligent summaries of your server's chat history. Whether you need quick recaps of missed conversations or automated daily summaries, ZSummarize delivers professional, customizable results.

---

## Features

### Core Functionality
- **AI-Powered Summaries**: Leverages Google Gemini models to create accurate, contextual summaries
- **Multiple Tone Styles**: Choose from serious, funny, sarcastic, poetic, or neutral tones
- **Flexible Message Limits**: Analyze anywhere from 1 to 500 messages per summary
- **Auto-Summary Scheduler**: Set up automated daily or weekly summaries
- **Secure API Storage**: Your Gemini API keys are encrypted with Fernet (AES-128) cryptography
- **Role-Based Permissions**: Separate access levels for managers and command users
- **Customizable Embeds**: Personalize colors, titles, thumbnails, and display options
- **Clean Mode**: Generate minimal summaries without metadata for cleaner presentation

### Supported AI Models
- Gemini 2.5 Pro
- Gemini 2.5 Flash
- Gemini 2.5 Flash Lite (default)
- Gemini 2.0 Flash
- Gemini 2.0 Flash Lite
- Gemini 2.0 Flash Experimental
- Gemini 1.5 Pro
- Gemini 1.5 Flash

---

## Getting Started

### Prerequisites
- A Discord server where you have Administrator permissions
- A Google Gemini API key (free at [Google AI Studio](https://makersuite.google.com/app/apikey))

### Initial Setup

1. **Invite the Bot**: Add ZSummarize to your Discord server
2. **Open Control Panel**: Run `/zsummarize` command
3. **Configure API Key**: 
   - Navigate to "AI Config" tab
   - Click "Set API Key"
   - Enter your Gemini API key
4. **Set Permissions** (Optional):
   - Go to "Permissions" tab
   - Assign Manager and/or Summarize roles
5. **Customize Settings**: Adjust tone, limits, and appearance to your liking

---

## Commands

### `/zsummarize`
Opens the interactive control panel for managing all bot settings.

**Required Permission**: Administrator or Manager Role

### `/summarize`
Generates an AI summary of channel messages.

**Parameters**:
- `channel` (optional): Target channel to summarize (defaults to current channel)
- `count` (optional): Number of messages to analyze, 1-500 (defaults to configured limit)
- `tone` (optional): Summary style - serious, funny, sarcastic, poetic, or neutral (defaults to configured tone)

**Examples**:
- `/summarize` - Summarize current channel with default settings
- `/summarize channel:#general count:50` - Summarize 50 messages from #general
- `/summarize tone:funny count:100` - Generate a humorous summary of 100 messages

**Required Permission**: Administrator, Manager Role, or Summarize Role

---

## Control Panel Guide

The control panel is accessed via `/zsummarize` and provides six main configuration tabs:

### Main Menu
Overview dashboard showing:
- System configuration status
- Auto-summary status
- Current AI model
- Active settings (tone, limit, interval)
- Assigned permission roles

### Settings Tab
Configure default operational parameters:
- **Default Tone**: Set the style for all summaries
- **Message Limit**: Default number of messages to analyze (1-500)
- **Default Channel**: Fallback channel for summaries

### AI Config Tab
Manage your Gemini API integration:
- **API Key Management**: Set or update your encrypted API key
- **Model Selection**: Choose from available Gemini models
- **Security Status**: View encryption status

### Embed Customization Tab
Personalize summary appearance:
- **Title**: Custom title for summary embeds
- **Color**: Hex color code for embed border
- **Thumbnail**: Optional image URL for embed corner
- **Show Tokens**: Toggle display of token usage statistics
- **Show Model**: Toggle display of AI model name
- **Clean Mode**: Enable minimal summaries without metadata
- **Clean Format**: Choose between embed or plain text for clean mode

### Scheduler Tab
Configure automated summaries:
- **Enable/Disable**: Toggle automatic summary generation
- **Interval**: Choose daily (1d) or weekly (7d) schedules
- **Post Channel**: Destination channel for auto-summaries
- **Last Run**: Timestamp of most recent automatic summary

### Permissions Tab
Control feature access:
- **Manager Role**: Full control panel access + summarize command
- **Summarize Role**: Command usage only (no panel access)
- **Clear Roles**: Remove all assigned permission roles

**Note**: Administrators always have full access regardless of role settings.

### Guide Tab
Built-in documentation and quick reference for all features.

---

## Permission System

ZSummarize uses a two-tier permission system:

### Administrators
- Always have complete access to all features
- Can use control panel and commands
- Cannot be restricted by role settings

### Manager Role
Users with this role can:
- Access and modify the control panel
- Use the `/summarize` command
- View logs and analytics
- Configure all bot settings

### Summarize Role
Users with this role can:
- Use the `/summarize` command
- Generate summaries on demand
- **Cannot** access the control panel
- **Cannot** modify settings

### Default Behavior
If no roles are configured:
- Only Administrators can use features
- Recommended to set at least one role for broader access

---

## Auto-Summary System

The scheduler automatically generates summaries at specified intervals:

### Setup Process
1. Open control panel (`/zsummarize`)
2. Navigate to "Scheduler" tab
3. Click "Enable" to activate auto-summaries
4. Set your preferred interval (1d or 7d)
5. Choose the post channel
6. Summaries will generate automatically!

### How It Works
- Bot checks every hour for scheduled summaries
- Generates summary when interval has elapsed
- Posts to configured channel automatically
- Records timestamp for next execution
- Uses default tone and message limit settings
- Requires API key to be configured

### Tracking
- View last execution time in Scheduler tab
- All auto-summaries are logged to disk
- Summaries include "Scheduled Auto-Summary" tag

---

## Customization Options

### Tone Styles
- **Serious**: Professional, formal analysis
- **Funny**: Humorous, entertaining summaries
- **Sarcastic**: Witty, ironic commentary
- **Poetic**: Artistic, expressive descriptions
- **Neutral**: Balanced, objective reporting

### Embed Display Options
Toggle metadata visibility:
- **Show Tokens**: Display AI token consumption
- **Show Model**: Show which Gemini model was used
- **Clean Mode**: Minimal summaries with just AI text
- **Clean Format**: Embed or plain text for clean mode

### Color Customization
- Use hex color codes (e.g., 5865F2 or #5865F2)
- Preview colors live in control panel
- Applies to all future summaries

---

## Data Storage

ZSummarize maintains several data files per server:

### Settings Files
- `settings_{guild_id}.json`: Bot configuration
- Stores preferences, roles, and operational parameters

### Secure Storage
- `api_{guild_id}.enc`: Encrypted API keys
- Protected with Fernet AES-128 encryption
- `cipher.key`: Encryption key (keep secure!)

### Cache Files
- `last_summary_{channel_id}.txt`: Most recent summary text
- Useful for referencing previous results

### Logs
- `summary_log_{date}.json`: Daily operation logs
- Tracks summaries, users, channels, and timestamps

---

## Security Features

### API Key Encryption
- All API keys encrypted at rest using Fernet
- AES-128 bit cryptographic protection
- Keys never stored in plain text
- Individual cipher key per bot instance

### Permission Controls
- Role-based access prevents unauthorized usage
- Separate panel access from command permissions
- Admin-only features always protected

### Data Isolation
- Server-specific settings and keys
- No cross-server data leakage
- Secure file permissions

---

## Best Practices

### API Key Management
- Never share your API key publicly
- Obtain keys from official Google AI Studio only
- Regenerate keys if compromised
- Use separate keys for different bots

### Permission Setup
- Assign Manager Role to trusted moderators only
- Use Summarize Role for general staff access
- Regularly audit role assignments
- Remove roles from departing team members

### Summary Usage
- Start with lower message counts (50-100)
- Increase limits based on channel activity
- Use appropriate tones for context
- Review auto-summary settings periodically

### Resource Management
- Higher message counts use more API tokens
- Pro models cost more than Lite variants
- Monitor token usage if on paid plan
- Schedule auto-summaries during low-traffic hours

---

## Troubleshooting

### "API key not configured"
**Solution**: Open control panel, go to AI Config, and set your Gemini API key.

### "You don't have permission"
**Solution**: Contact server administrators to assign you Manager or Summarize role.

### "Channel not found"
**Solution**: Verify channel ID is correct and bot has access to that channel.

### "Invalid tone/interval/color"
**Solution**: Check format requirements in control panel tooltips or guide tab.

### Auto-summaries not working
**Possible causes**:
- Auto-summary disabled in Scheduler tab
- No post channel configured
- API key missing or invalid
- Not enough time elapsed since last run

### Summary seems inaccurate
**Solutions**:
- Increase message count for more context
- Try different AI model (Pro for better quality)
- Adjust tone to match content style
- Ensure messages contain substantial content

---

## Tips & Tricks

### Optimal Message Counts
- **Quick Updates**: 20-50 messages
- **Standard Recaps**: 100-200 messages
- **Deep Dives**: 300-500 messages

### Tone Selection Guide
- **Serious**: Reports, announcements, important discussions
- **Funny**: Casual chat, memes, entertainment channels
- **Sarcastic**: Debates, roasts, competitive channels
- **Poetic**: Creative writing, art channels, storytelling
- **Neutral**: Mixed content, general channels

### Clean Mode Usage
- Enable for public-facing summaries
- Use for social media posts
- Disable for internal tracking
- Combine with plain text for maximum minimalism

### Scheduling Strategies
- Daily: Active servers with constant chatter
- Weekly: Slower servers or recap channels
- Match interval to community activity patterns

---

## Limitations

- Maximum 500 messages per summary
- Summaries limited by Gemini token constraints
- Auto-summaries check hourly (not minute-precise)
- Bot messages excluded from analysis
- Requires channel read permissions

---

## Support

For assistance with ZSummarize:
1. Check the built-in Guide tab in control panel
2. Contact your server administrators
3. Review this documentation thoroughly
4. Join the support server (if available)

---

## Credits

**ZSummarize v1.0**  
Created by **TheHolyOneZ (TheZ)**

Powered by Google Gemini AI  
Built for Discord communities worldwide

---

## License

License at the very top of the file!
