# Dvand - Standardized Platform Specifications

## Video Content Standards

- **Duration**: 15-60 seconds (standardized across all user types)
- **Submission Limit**: 2 videos per challenge per creator
- **Tag Limit**: 8 tags maximum per video
- **File Size**: Maximum 50MB per video
- **Formats**: MP4, MOV, AVI supported

## Challenge Structure

- **Winner Selection**: Single winner per challenge (winner-takes-all)
- **Prize Amounts**: ₹5,000 (weekly), ₹25,000 (monthly)
- **Leaderboard Display**: Top 3 positions shown for engagement (2nd/3rd are visual only)
- **Judging**: Shor Score algorithm with admin discretionary override

## Voting System

### Logged-In Users (Signed In)

- **Daily Allocation**: 50 votes per day
- **Carryover**: Unused votes carry to next day
- **Weekly Reset**: All votes reset at start of each week
- **Interface**: Balloon slider for vote allocation (1 to max available)

### Non-Logged-In Users (Anonymous)

- **Daily Allocation**: 5 votes per day
- **Reset**: Daily reset (no carryover)
- **Maximum**: 5 votes at any time
- **Interface**: Same balloon slider mechanism

## Content Access Limits

### Non-Logged-In Users

- **Video Viewing**: 10 videos per day
- **Voting**: 5 votes per day
- **Reset**: 24-hour rolling period
- **Purpose**: Load testing, user behavior analysis, marketing insights

### Logged-In Users

- **Video Viewing**: Unlimited
- **Enhanced Features**: Following, reactions, notifications, full leaderboards

## KYC Verification Tiers

### Partial KYC (Content Creation)

- **Purpose**: Compliance with Indian content creation laws
- **Required For**: Video uploads and challenge participation
- **Documents**: Basic identity verification

### Full KYC (Prize Winners)

- **Purpose**: Cash prize disbursement and tax compliance
- **Trigger**: Only when winning a challenge
- **Documents**: Complete identity + banking details
- **Process**: Partial KYC is subset of Full KYC

## Prize Payment System

### Recommended Approach

- **Primary**: Business payment service (Razorpay/Cashfree/PayU Payouts)
  - Automatic TDS handling
  - Bulk payment processing
  - Audit trail maintenance
  - UPI as underlying transfer method
- **Fallback**: Direct UPI for exceptional cases
- **Tax Compliance**: Automatic TDS deduction and documentation

## Platform Strategy

- **Primary Platform**: Mobile (mobile-first approach)
- **Language**: English only (initial launch)
- **Admin Team**: 3-person team handling all operations
- **Moderation Capacity**: 200+ videos per weekly challenge (manageable)

## User Flow Priorities

### Content Moderation (Priority 1)

- Video review and approval/rejection
- Policy violation handling
- Appeal management

### Challenge Management (Priority 2)

- Challenge creation and scheduling
- Real-time monitoring
- Winner selection process

### User Management & KYC (Priority 3)

- Creator verification processing
- Account management
- Verification expiry tracking

### Prize Disbursement (Priority 4)

- Winner eligibility verification
- Payment processing
- Dispute resolution

### Platform Monitoring (Priority 5)

- Basic statistics and health metrics
- Performance tracking

### Policy & Compliance (Priority 6)

- Community guidelines management
- Regulatory compliance
- User safety measures

## Technical Implementation Notes

- **Session Management**: JWT tokens with refresh
- **Video Processing**: On-device optimization before upload
- **Real-time Updates**: WebSocket connections for live features
- **Caching**: Offline capability for recently viewed content
- **Security**: Multi-factor admin authentication, encrypted sensitive data storage

## Error Handling Standards

- **User-Friendly Messages**: Clear, actionable error descriptions
- **Recovery Options**: Automatic retry with manual override
- **Data Preservation**: Auto-save drafts and user progress
- **Escalation Paths**: In-app help → WhatsApp support → Email support
- **Privacy Protection**: No sensitive data in error logs

## Success Metrics (Initial Launch)

- **User Engagement**: Load testing and behavior analysis
- **Content Quality**: Moderation efficiency and creator satisfaction
- **Technical Performance**: App stability and feature adoption
- **Business Validation**: Challenge participation and winner conversion rates

## Future Considerations

- **Feature Expansion**: Analytics and optimization tools post-launch
- **Localization**: Hindi and regional language support
- **Advanced Features**: Enhanced creator tools and viewer engagement options

This specification serves as the single source of truth for all DVAND development and should be referenced to maintain consistency across all user stories and technical implementations.
