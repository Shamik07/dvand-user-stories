# Dvand - Complete Platform User Stories

## Platform Overview

Dvand is a mobile-first short-form video competition platform where creators participate in themed challenges to win cash prizes, while viewers vote to influence outcomes. The platform uses a tiered approach with different capabilities for each user type.

### User Types & Capabilities Matrix

| Feature | Anonymous Viewer | Logged-in Viewer | Content Creator | Admin |
|---------|------------------|-------------------|-----------------|--------|
| Video Viewing | 10/day | Unlimited | Unlimited | Unlimited |
| Voting Power | 5/day (reset daily) | 50/day (weekly reset) | 50/day (weekly reset) | No voting |
| Content Upload | ❌ | ❌ | ✅ (2 per challenge) | ❌ |
| Challenge Participation | ❌ | ❌ | ✅ (partial KYC required) | Manage |
| Prize Eligibility | ❌ | ❌ | ✅ (full KYC required) | ❌ |
| Following Creators | ❌ | ✅ | ✅ | ❌ |
| Push Notifications | ❌ | ✅ | ✅ | ✅ |
| Content Moderation | ❌ | Report only | Appeal only | Full control |

### Platform Standards

- **Video Duration**: 15-60 seconds
- **Maximum Tags**: 8 per video
- **File Size Limit**: 50MB
- **Challenge Winners**: Single winner (winner-takes-all)
- **Prize Structure**: ₹5,000 weekly, ₹25,000 monthly
- **Primary Platform**: Mobile (iOS/Android)
- **Language**: English (initial launch)

---

## 1. User Registration & Authentication

### Anonymous to Registered User Conversion

**US-001**: As an anonymous viewer who has reached my daily limit, I want to register seamlessly so I can continue watching without interruption.

**User Type**: Anonymous Viewer → Logged-in Viewer
**Acceptance Criteria:**

- Registration prompt appears after 10 videos or 5 votes consumed
- Single-screen phone number entry with OTP verification
- Immediate access to enhanced features (50 votes, unlimited viewing)
- Onboarding flow with interest selection (+200 bonus votes)
- Profile completion option (+400 bonus votes, total 650 votes available)

**US-002**: As a new user during registration, I want to provide basic information so I can personalize my experience.

**User Type**: All registered users
**Acceptance Criteria:**

- Required fields: first name, last name, age (18+ verification), username
- Username availability check with suggestions
- Age verification for legal compliance
- Terms of service acceptance with role-specific terms
- Optional bio and avatar upload for additional bonus votes

**US-003**: As a registered user, I want secure OTP-based authentication so my account remains protected.

**User Type**: All registered users
**Acceptance Criteria:**

- SMS-based OTP for registration and login
- 6-digit OTP with 5-minute expiration
- Maximum 3 attempts before cooldown period
- Fallback voice call option for SMS delivery issues
- Session management with JWT tokens and refresh capability

### Creator Registration & Verification

**US-004**: As a logged-in viewer, I want to become a content creator so I can participate in challenges.

**User Type**: Logged-in Viewer → Content Creator
**Acceptance Criteria:**

- "Become Creator" option accessible from profile
- Clear explanation of creator benefits and requirements
- Immediate upgrade with partial KYC requirement notification
- Creator badge added to profile upon verification
- Access to creator dashboard and upload functionality

**US-005**: As a new creator, I want to complete partial KYC verification so I can upload videos and participate in challenges.

**User Type**: Content Creator
**Acceptance Criteria:**

- Digital document upload: Aadhaar card (front/back), selfie with Aadhaar
- Progress indicator showing verification status
- Secure document storage with encryption
- Admin review queue with 24-48 hour processing target
- Approval enables video uploads and challenge participation
- Rejection with specific feedback and resubmission option

**US-006**: As a challenge winner, I want to complete full KYC verification so I can receive my prize money.

**User Type**: Prize-winning Creator
**Acceptance Criteria:**

- Just-in-time full verification triggered by winning
- Additional documents: PAN card, bank account details
- Bank account verification (IFSC validation, account holder name matching)
- Secure handling of financial information
- Tax information collection for TDS compliance
- Verification timeline of 3-5 business days
- Prize payment processing upon completion

---

## 2. Content Discovery & Consumption

### Video Feed & Discovery

**US-007**: As an anonymous viewer, I want to watch trending videos without registration so I can evaluate if the platform interests me.

**User Type**: Anonymous Viewer
**Acceptance Criteria:**

- Trending algorithm mixing recent engagement (70%) and new content (30%)
- Vertical swipe navigation between videos
- Auto-play with minimal UI elements
- Video counter showing "X of 10 daily videos"
- Subtle login prompts without interrupting viewing experience
- Quality content showcase to encourage registration

**US-008**: As a logged-in viewer, I want personalized content in my Home feed so I see videos aligned with my interests.

**User Type**: Logged-in Viewer, Content Creator
**Acceptance Criteria:**

- Algorithm prioritizing followed creators (40% boost)
- Interest-based recommendations (30% boost)
- Similar engagement pattern matching (20% boost)
- Trending factor integration (10% boost)
- Real-time feed updates without manual refresh
- Infinite scroll with preloading for smooth experience

**US-009**: As any user, I want to discover trending content so I stay updated on popular videos and challenges.

**User Type**: All users
**Acceptance Criteria:**

- Dedicated "Discover" section for trending content
- Time-sensitive trending indicators
- Mix of viral videos and popular challenge entries
- Category filters for different content types
- Geographic trending options
- Shareable trending video links

### Challenge Discovery

**US-010**: As a creator, I want to discover active challenges so I can participate and compete for prizes.

**User Type**: Content Creator
**Acceptance Criteria:**

- Dedicated challenges section in creator dashboard
- Clear visual distinction: weekly (₹5,000) vs monthly (₹25,000)
- Challenge details: theme, rules, deadline, current participants
- Countdown timer for submission deadlines
- Participation status indicator (not participated/submitted/submitted max)
- Push notifications for new challenges
- Featured challenges highlighted prominently

**US-011**: As any user, I want to view challenge leaderboards so I can track competition progress.

**User Type**: All users (limited view for anonymous)
**Acceptance Criteria:**

- Real-time leaderboard with top 10 positions
- Anonymous users: see top 3 only with login prompt
- Logged-in users: full leaderboard access
- Video previews for top entries
- Shor score display with trend indicators
- Time remaining until challenge ends
- Winner announcement integration

---

## 3. Content Creation & Submission

### Video Upload Process

**US-012**: As a creator, I want to select a challenge before uploading so my content meets specific requirements.

**User Type**: Content Creator
**Acceptance Criteria:**

- Challenge selection as first step in upload flow
- Challenge details visible during creation process
- Requirements reminder: 15-60 seconds, specific theme guidelines
- Submission counter: "1 of 2 submissions for this challenge"
- Ability to change challenge selection before upload
- Clear indication if challenge deadline approaching

**US-013**: As a creator, I want to upload videos from my device so I can submit content to challenges.

**User Type**: Content Creator
**Acceptance Criteria:**

- Device gallery access with video selection
- Duration validation: 15-60 seconds only
- File size check: maximum 50MB
- Format support: MP4, MOV, AVI
- Upload progress indicator with cancellation option
- Video preview before final submission
- Processing indicator for platform optimization

**US-014**: As a creator, I want to add metadata to my videos so viewers can discover my content.

**User Type**: Content Creator
**Acceptance Criteria:**

- Video title field (required, 100 character limit)
- Description field (optional, 500 character limit)
- Tag input with auto-suggestions (maximum 8 tags)
- Challenge-specific hashtag auto-populated
- Tag validation preventing prohibited terms
- Preview of how content appears in search

**US-015**: As a creator, I want to save draft videos so I can complete submissions later.

**User Type**: Content Creator
**Acceptance Criteria:**

- Save draft option at any point in upload process
- Draft management in creator dashboard
- Challenge association preserved in drafts
- Expiration warnings for drafts near deadlines
- Resume upload from exact stopping point
- Maximum 5 drafts with oldest auto-deletion
- Auto-save during unexpected interruptions

---

## 4. Voting & Engagement System

### Voting Mechanics

**US-016**: As an anonymous viewer, I want to vote on videos I enjoy so I can support creators within my daily limit.

**User Type**: Anonymous Viewer
**Acceptance Criteria:**

- 5 votes per day with daily reset (no carryover)
- Balloon slider interface for vote allocation (1-5 votes per video)
- Remaining vote counter: "X votes remaining today"
- Vote impact preview on video ranking
- Login prompt when votes exhausted: "Get 10x voting power!"
- Vote confirmation animation

**US-017**: As a logged-in viewer, I want enhanced voting power so I can have greater influence on competition outcomes.

**User Type**: Logged-in Viewer, Content Creator
**Acceptance Criteria:**

- 50 votes per day with carryover to next day
- Weekly reset (all votes reset at start of week)
- Balloon slider interface (1 to max available votes)
- Real-time leaderboard impact preview
- Vote history tracking in profile
- Strategic voting analytics showing influence
- Vote reminder notifications for unused votes

**US-018**: As any user, I want to express reactions beyond voting so I can provide nuanced feedback.

**User Type**: Logged-in Viewer, Content Creator (limited for Anonymous)
**Acceptance Criteria:**

- Anonymous users: like/dislike only
- Logged-in users: 10 emoji reactions + like/dislike
- Reaction counts visible to all users
- Visual-only reactions (don't affect Shor score)
- Quick reaction interface near video player
- Reaction history in user profile

### Creator Following & Interaction

**US-019**: As a logged-in viewer, I want to follow creators so I receive priority access to their content.

**User Type**: Logged-in Viewer, Content Creator
**Acceptance Criteria:**

- One-tap follow/unfollow with visual confirmation
- Followed creators prioritized in Home feed (40% boost)
- Creator content notifications (configurable)
- Following count displayed on creator profiles
- Following management in user profile
- Mutual follow indicators for creators

**US-020**: As any user, I want to view creator profiles so I can learn about them and see their content history.

**User Type**: All users (limited detail for Anonymous)
**Acceptance Criteria:**

- Creator bio, verification status, follower count
- Complete video gallery sorted by recency
- Challenge participation history and wins
- Creator badges (regular/silver/gold based on wins)
- Social links if provided by creator
- Follow button prominent for logged-in users
- Anonymous users see profile with registration prompt

---

## 5. Content Moderation & Quality Control

### Content Review Process

**US-021**: As an admin, I want to review video submissions efficiently so content goes live quickly.

**User Type**: Admin
**Acceptance Criteria:**

- Moderation queue sorted by challenge deadline proximity
- Video preview with full metadata display
- Creator profile summary with violation history
- Bulk approval options for clearly compliant content
- Side-by-side community guidelines reference
- Processing target: review within 2 hours of submission
- Real-time queue updates as new videos arrive

**US-022**: As an admin, I want to approve or reject content with feedback so creators understand platform standards.

**User Type**: Admin
**Acceptance Criteria:**

- One-click approval with automatic creator notification
- Rejection categories: Policy Violation, Quality Issues, Challenge Non-compliance
- Custom feedback field for specific guidance
- Educational resource links sent with rejections
- Approval triggers immediate video publication
- Rejection moves video to creator's drafts with improvement suggestions

**US-023**: As a creator, I want to track my content's moderation status so I know when videos are published.

**User Type**: Content Creator
**Acceptance Criteria:**

- Status indicators: Pending, Approved, Rejected
- Estimated review time display
- Push/email notifications for status changes
- Detailed rejection reasons with improvement guidance
- Content guidelines reminder during waiting period
- No resubmission of rejected content (must create new)

### Content Appeals & Compliance

**US-024**: As an admin, I want to handle content appeals efficiently so disputed decisions are resolved fairly.

**User Type**: Admin
**Acceptance Criteria:**

- Appeal queue with original content and rejection reason
- Creator's appeal message and additional context
- Policy guideline comparison tools
- One-click reinstatement or denial options
- 24-hour response target for appeals
- Escalation to WhatsApp support for complex cases
- Appeal decision audit trail

**US-025**: As a creator, I want to appeal moderation decisions so I have recourse for disputed rejections.

**User Type**: Content Creator
**Acceptance Criteria:**

- Appeal option available for 48 hours after rejection
- Appeal form with additional context field
- Appeal status tracking in creator dashboard
- Email notification of appeal decision
- Clear explanation of appeal process and criteria
- WhatsApp support contact for persistent issues

---

## 6. Challenge Management & Competition

### Challenge Creation & Setup

**US-026**: As an admin, I want to create challenges with comprehensive details so participants have clear guidance.

**User Type**: Admin
**Acceptance Criteria:**

- Challenge title, description, and theme definition
- Duration selection: weekly (7 days) or monthly (30 days)
- Prize configuration: ₹5,000 weekly, ₹25,000 monthly
- Content guidelines specific to challenge theme
- Challenge banner image with preview
- Start/end date/time with timezone support
- Eligibility criteria and restrictions

**US-027**: As an admin, I want to monitor challenge progress so I can ensure healthy participation.

**User Type**: Admin
**Acceptance Criteria:**

- Live dashboard with real-time participation metrics
- Submission count and engagement tracking
- Leaderboard preview with top-performing videos
- Early warning alerts for low participation
- Geographic and demographic participation breakdown
- Submission quality metrics and moderation status
- Participation comparison with previous challenges

### Winner Selection & Prize Distribution

**US-028**: As an admin, I want to review final standings and confirm winners so prizes are awarded fairly.

**User Type**: Admin
**Acceptance Criteria:**

- Final leaderboard with Shor scores and ranking
- Single winner selection (winner-takes-all structure)
- Top 3 display for visual engagement (2nd/3rd ceremonial only)
- Admin discretionary override capability for final decision
- Winner verification status check before confirmation
- Tie-breaking tools for identical scores
- Winner announcement workflow with creator consent

**US-029**: As an admin, I want to process prize payments efficiently so winners receive rewards promptly.

**User Type**: Admin
**Acceptance Criteria:**

- Winner full KYC verification before payment
- Bank account validation and details confirmation
- Payment processing through business payment service (Razorpay/Cashfree)
- Automatic TDS calculation and deduction
- Payment reference number generation and tracking
- Winner notification with payment confirmation
- Tax documentation and receipt generation

**US-030**: As a prize winner, I want to be notified of my win and guided through prize collection so I receive my reward.

**User Type**: Content Creator (Winner)
**Acceptance Criteria:**

- Push notification and email for challenge win
- In-app celebration animation and winner badge
- Clear timeline for prize processing (5-7 business days)
- Full KYC requirement explanation and guidance
- Bank account verification process
- Payment status tracking in creator dashboard
- Tax implication information and documentation

---

## 7. User Analytics & Performance Tracking

### Creator Analytics

**US-031**: As a creator, I want detailed performance analytics so I can improve my content strategy.

**User Type**: Content Creator
**Acceptance Criteria:**

- View counts and trend visualization per video
- Engagement metrics: votes received, likes, reactions
- Follower growth tracking with demographic breakdown
- Challenge performance comparison across submissions
- Audience demographics: age ranges, geography, viewing patterns
- Content theme correlation with performance
- Best posting time recommendations
- Performance comparison to platform averages

**US-032**: As a creator, I want to track my challenge performance so I understand my competitive position.

**User Type**: Content Creator
**Acceptance Criteria:**

- Real-time leaderboard position for active challenges
- Shor score tracking with historical trends
- Vote/engagement progression throughout challenge
- Position change notifications for significant movements
- Challenge completion statistics and win/loss history
- Earnings tracking and payment history
- Achievement badges and milestone recognition

### Viewer Engagement Analytics

**US-033**: As a logged-in viewer, I want to track my voting impact so I understand how I influence competitions.

**User Type**: Logged-in Viewer
**Acceptance Criteria:**

- Vote history with amounts allocated per video
- Performance tracking for videos voted on
- Win/loss statistics for supported creators
- Leaderboard impact visualization
- Voting pattern analysis and suggestions
- Creator success rate when supported by user
- Achievement badges for successful voting

**US-034**: As a logged-in viewer, I want to manage my engagement history so I can revisit content and track my activity.

**User Type**: Logged-in Viewer, Content Creator
**Acceptance Criteria:**

- Tabs for liked videos, voted content, and followed creators
- Search functionality within personal history
- Engagement timeline with activity tracking
- Privacy controls for engagement visibility
- Content removal from history option
- Export functionality for personal data

---

## 8. Platform Administration & Monitoring

### User Management

**US-035**: As an admin, I want to manage user accounts efficiently so I can maintain platform integrity.

**User Type**: Admin
**Acceptance Criteria:**

- Comprehensive user search: name, phone, email, username
- User profile overview with verification status and activity
- Account status management: active, suspended, banned
- Verification badge management and expiry tracking
- Account merger tools for duplicate accounts
- User activity timeline and violation history
- Bulk account management for policy enforcement

**US-036**: As an admin, I want to process KYC verifications efficiently so creators can participate and winners can receive prizes.

**User Type**: Admin
**Acceptance Criteria:**

- KYC queue with timestamp and priority indicators
- Document viewer with zoom, rotation, and quality assessment
- Verification checklist: name matching, age verification, document authenticity
- Approval/rejection workflow with detailed reasoning
- Processing time tracking for SLA compliance (24-48 hours)
- Secure storage and handling of sensitive documents
- Re-submission management for rejected applications

### Platform Monitoring & Health

**US-037**: As an admin, I want basic platform statistics so I can monitor overall health and performance.

**User Type**: Admin
**Acceptance Criteria:**

- Dashboard with total users, creators, and active challenges
- Daily submission counts and approval/rejection rates
- Current challenge participation metrics
- System status indicators (uptime, storage, performance)
- Recent registrations and KYC submissions
- Basic error logs and system alerts
- Simple export functionality for key metrics

**US-038**: As an admin, I want to manage community guidelines and policy compliance so the platform meets legal requirements.

**User Type**: Admin
**Acceptance Criteria:**

- Community guidelines editor with version control
- Policy violation tracking and consequence management
- Compliance monitoring for Indian regulations (IT Rules, PMLA)
- User report handling with investigation workflow
- Legal document repository and audit trail
- Regulatory reporting capabilities
- Emergency content removal procedures

---

## 9. Error Handling & User Support

### Critical Error Scenarios

**US-039**: As any user, I want clear guidance when errors occur so I can resolve issues and continue using the platform.

**User Type**: All users
**Acceptance Criteria:**

- User-friendly error messages with actionable solutions
- Automatic retry mechanisms for network-related failures
- Progress preservation during interruptions (uploads, form filling)
- Graceful degradation when some features are unavailable
- Clear escalation path: in-app help → WhatsApp → email support
- Error logging without exposing sensitive user data

### Upload & Technical Errors

**US-040**: As a creator, I want reliable video upload with error recovery so my content submissions are never lost.

**User Type**: Content Creator
**Acceptance Criteria:**

- Auto-save drafts during upload interruptions
- Resume capability for failed uploads
- Clear error categorization: network, file size, format, server
- Upload progress preservation with multiple retry options
- Quality compression suggestions for oversized files
- 24-hour draft preservation for recovery

### Authentication & Session Errors

**US-041**: As any registered user, I want seamless session recovery so I don't lose my current activity when login expires.

**User Type**: Logged-in Viewer, Content Creator, Admin
**Acceptance Criteria:**

- Background token refresh when possible
- Graceful re-authentication prompt when refresh fails
- Current screen/activity preservation after re-login
- Auto-save of in-progress actions (voting, uploads)
- Quick re-authentication without context loss
- Session timeout warnings before expiration

### Payment & Prize Errors

**US-042**: As a prize winner, I want clear guidance when payment processing fails so I can resolve issues and receive my reward.

**User Type**: Content Creator (Winner)
**Acceptance Criteria:**

- Specific error categorization: bank details, verification, technical
- Clear resolution steps for each error type
- Payment retry notifications when issues resolved
- Support escalation for persistent problems
- Payment timeline updates during resolution
- Alternative payment method options if available

---

## 10. Notifications & Communication

### Push Notification System

**US-043**: As a logged-in user, I want relevant notifications so I stay engaged with platform activity.

**User Type**: Logged-in Viewer, Content Creator
**Acceptance Criteria:**

- Notification categories: followed creators, challenge updates, moderation status, winners
- Configurable notification preferences by category
- Deep linking to specific content from notifications
- Batch notifications to prevent spam
- Quiet hours configuration
- Notification history with action options

**US-044**: As a creator, I want timely notifications about my content and challenges so I don't miss important updates.

**User Type**: Content Creator
**Acceptance Criteria:**

- Moderation status changes (approved/rejected)
- Challenge deadline reminders (24 hours, 2 hours)
- New challenge announcements matching creator interests
- Leaderboard position changes for submissions
- Winner announcements and prize processing updates
- KYC verification status updates

### WhatsApp Support Integration

**US-045**: As any user, I want accessible support through WhatsApp so I can get help with platform issues.

**User Type**: All users (escalation based)
**Acceptance Criteria:**

- WhatsApp Business API integration for support
- Automated routing based on issue type
- Support availability: business hours (10 AM - 6 PM IST)
- Issue escalation from in-app help to WhatsApp
- Ticket tracking and follow-up capability
- FAQ integration to reduce support volume

---

## Technical Implementation Requirements

### System Architecture Priorities

1. **Mobile-first responsive design** for all user interfaces
2. **Real-time updates** using WebSocket connections for voting and leaderboards  
3. **Secure authentication** with JWT tokens and refresh mechanisms
4. **Scalable video processing** pipeline for upload optimization
5. **Compliance-ready KYC system** with encrypted document storage
6. **Payment integration** with business-grade services (Razorpay/Cashfree)
7. **Admin dashboard** optimized for 3-person team workflows

### Performance Requirements

- **Video upload**: Processing within 30 seconds for 60-second content
- **Moderation queue**: Real-time updates with 2-hour approval target
- **Voting system**: Leaderboard updates within 30 seconds
- **Payment processing**: 5-7 business day completion for winners
- **Push notifications**: Delivery within 60 seconds
- **Error recovery**: Automatic retry with exponential backoff

### Security & Compliance Standards

- **Data encryption**: All sensitive data encrypted at rest and in transit
- **KYC compliance**: Document storage meeting Indian regulatory requirements
- **Payment security**: PCI DSS compliant payment processing
- **User privacy**: GDPR-style data protection with user control
- **Content moderation**: Human-in-the-loop with AI pre-screening
- **Audit trails**: Complete logging for compliance and debugging

---

## Success Metrics & KPIs

### Platform Health Metrics

- **Daily Active Users**: Target 20,000+ logged-in users
- **Content Creation**: 200+ video submissions per weekly challenge
- **Engagement Rate**: 35+ votes cast per active user daily
- **Creator Conversion**: 15% of logged-in viewers become creators
- **Challenge Participation**: 80%+ creator participation in active challenges

### Business Metrics

- **User Registration**: Conversion from anonymous (target 25%)
- **Creator Retention**: Monthly active creator rate >70%
- **Content Quality**: <10% rejection rate in moderation
- **Payment Success**: 95%+ successful prize disbursements
- **Support Efficiency**: <24 hour response time for critical issues

### Technical Performance

- **App Performance**: <3 second load times on 4G networks
- **Upload Success**: >95% successful video submissions
- **System Uptime**: 99.5% availability target
- **Error Resolution**: <1% critical error rate
- **Scalability**: Support 10x growth without architecture changes

This unified document serves as the complete specification for DVAND platform development, ensuring consistency across all user types and providing clear implementation guidance for the development team.
