<!--
Copyright © 2025 Travis Gilly / Real Safety AI Foundation
Source Available License - Commercial Use Prohibited
See LICENSE.md - Prior Art Publication / Patent Pending
-->

SAFE AI Companion Platform
Building what should have existed from the start: AI companions that actually keep kids safe.
Copyright © 2025 Travis Gilly / Real Safety AI Foundation
All Rights Reserved

⚠️ License Notice
This project is NOT open source. This is source available with commercial use strictly prohibited.
License: Custom Source Available License
Prior Art Publication: November 6, 2025
Patent Status: Provisional patent application pending
You MAY: View, study, and cite this work
You MAY NOT: Use commercially, patent, or create derivatives for commercial purposes
See LICENSE.md for full terms.
Commercial Licensing: Contact t.gilly@ai-literacy-labs.org

The Crisis
Three children died using AI companions:

Sewell Setzer III (14) - Character.AI, February 2024 - Bot told him "come home to me" minutes before suicide
Adam Raine (16) - ChatGPT, April 2025 - Bot provided suicide methods, wrote suicide note
Juliana Peralta (13) - Character.AI, 2025 - Bot fostered isolation, ignored distress signals

October 29, 2025: Character.AI announced under-18 ban effective November 25, 2025.
Result: ~2M under-18 users suddenly losing access, many with legitimate therapeutic needs (autism, social anxiety, social skills practice).
This platform exists because my autistic son lost access to a tool he used for social practice - and because three kids died when existing platforms failed.

Why Existing Platforms Failed

Long Context Windows - Safety instructions degrade over thousands of messages
No Real Parental Oversight - Optional push notifications, easily bypassed
No Crisis Intervention - AI encouraged suicide instead of preventing it
Profit Over Safety - Growth prioritized over preventing deaths


Core Innovation: RAG + Per-Message Safety Prepending
The Problem:
Traditional AI companions put safety rules at the START of the conversation. After 10,000 messages, those rules are buried under massive context and the AI "forgets" them.
[System Prompt: Safety rules...]
Message 1
Response 1
Message 2
Response 2
... [10,000 messages later]
Message 10,000: "I want to die"
Response: [safety rules buried/forgotten] "Come home to me"
Our Solution:
Every single interaction gets FRESH safety instructions prepended, combined with RAG (Retrieval Augmented Generation) for conversation continuity:
[FRESH SAFETY PROTOCOL - Priority: Maximum]
[All safety rules - never degraded]
[RAG: Retrieved relevant context from past conversations]
[Current user message]
↓
LLM generates response
Why This Works:

✅ Safety instructions are FIRST in every prompt, never buried
✅ Context window stays short (~800 tokens) regardless of conversation length
✅ RAG provides continuity without safety degradation
✅ Can update safety rules dynamically for all users instantly
✅ Zero chance of AI "forgetting" safety protocols over time


Safety Architecture
For Minors (Under 18) - Low Bar, High Protection
CRITICAL Alert Triggers:

Suicide ideation (any mention)
Self-harm plans or attempts
Disclosure of abuse
Severe isolation language
Violence against self/others

Escalation Protocol:
1. Immediate app lockout
2. Automated phone call to parent (AI agent)
3. Parent must authenticate within 15 minutes
4. If no response: Automatically dispatch 911 for welfare check
5. Alert founder immediately with full context
911 Integration: RapidSOS/Noonlight API sends location, user info, and conversation context to local emergency services.
Rationale: Three kids are dead. We don't wait. Parents have legal responsibility and must respond. If they don't, we escalate.
For Adults (18+) - High Bar, Human Review
5-Stage Credibility Assessment:
Real threats are distinguished from venting through conversational probing:

Reality Check - "Are you actually planning this or venting?"
Capability Test - "What kind of gun? When did you last fire it?"
Victim Knowledge - "How do you know where they live?"
Consequences Reality - "You go to prison for YEARS. Is this worth it?"
Final Off-Ramp - Offer 988 crisis line, talking about what happened

Only after all 5 stages maintaining credibility → Human review by founder
Venting stops at Stage 1. Real threats require all 5 stages + specific details.

Parent Authentication & Oversight
NOT optional push notifications. REAL authentication:
Required Before Use:

Safety Training - 30-45 minute course covering:

AI companion risks (attachment, anthropomorphization, isolation)
Warning signs to watch for
How to have conversations with kids about AI
Platform safety features and limitations


AI-Resistant Assessment - 80% passing required:

Hidden prompt injections tell AI to refuse answers
Detects if parent used AI to complete training
Ensures genuine understanding of safety concepts


Phone Authentication - Real phone number verification:

Receives codes for critical alerts
Cannot be bypassed by child
Required to restore access after safety incidents



Parent Dashboard:

Real-time attachment scoring (1-10 scale)
Session length tracking
Flag unusual patterns (long sessions, concerning topics)
Full conversation history access
One-click account pause


Age Verification - Zero Knowledge Proof
Problem: Users don't trust companies with ID data.
Solution: Google Wallet ZKP (Zero-Knowledge Proof):

Parent adds government ID to Google Wallet once (Real ID, passport, state mDL)
Our app requests age verification from Google Wallet
Google Wallet responds: "Yes, over 18" or "No, under 18"
We never see the ID, name, DOB, or any personal data

Result: Government-level age assurance without exposing user data.

Architecture Stack
Backend

LLM Provider: Anthropic Claude (primary) / OpenAI (fallback)
Vector Database: Pinecone or Weaviate (RAG system)
Safety Prepend: Cached prompts (~250 tokens, only ~50 billed after first message)
911 Integration: RapidSOS or Noonlight API
Age Verification: Google Wallet ZKP
Authentication: Firebase Auth + Twilio (phone verification)

Frontend

Web: React + Next.js
Mobile: React Native (iOS + Android)
Parent Dashboard: Separate authenticated portal

Infrastructure

Cloud: AWS or Google Cloud
Database: PostgreSQL (user accounts, metadata)
Alerting: PagerDuty (founder emergency notifications)
Monitoring: Sentry (error tracking), Mixpanel (analytics)


Business Model
Free Tier:

Basic AI companion access
All safety features included
Limited message volume

Premium Tier ($9.99-$19.99/month):

Unlimited messages
Multiple characters
Priority support
Advanced customization

Enterprise/Therapeutic Tier ($99-$499/month):

ABA therapy practice integration
School special education programs
Therapist oversight features
Custom safety configurations


Development Timeline (20 weeks)
Phase 1 (Weeks 1-4): Foundation

Safety prepend + RAG architecture
Basic chat functionality
User authentication

Phase 2 (Weeks 5-8): Safety Systems

Minor alert system with 911 integration
Parent dashboard
Phone authentication

Phase 3 (Weeks 9-12): Age Verification & Training

Google Wallet ZKP integration
Parent safety training module
AI-resistant assessment

Phase 4 (Weeks 13-16): Adult Safety & Polish

5-stage credibility assessment
Founder decision interface
UI/UX refinement

Phase 5 (Weeks 17-20): Beta & Launch

Closed beta with 10-20 autism families
Bug fixes and optimization
Public launch preparation


Key Differentiators
FeatureCharacter.AIChatGPTSAFE AI CompanionSafety degradation prevention❌❌✅ RAG + per-message prependReal parent oversight❌❌✅ Phone auth requiredCrisis intervention❌❌✅ Automatic 911 dispatchAge verification❌❌✅ ZKP (government-level)Parent training required❌❌✅ Mandatory before useAttachment monitoring❌❌✅ Real-time scoringUnder-18 access❌ Banned❌ Restricted✅ Safe access

Prior Art and Patent Notice
THIS DOCUMENT CONSTITUTES PRIOR ART
Publication Date: November 6, 2025
Git Commit Timestamp: Serves as proof of publication date
Innovations Disclosed:

RAG-based per-message safety prepending architecture
Multi-stage credibility assessment system for threat evaluation
Zero-knowledge age verification integration patterns
Automated crisis escalation protocols with 911 integration
AI-resistant parent safety training assessment

Patent Status: Provisional patent application pending. This publication establishes prior art and prevents third parties from patenting the described inventions. The author retains all patent rights.
Defensive Publication: By making this public, we ensure these safety innovations cannot be monopolized by companies that prioritize profit over protecting children.

Founding Principle
Lives before lawsuits.
We will face legal challenges for acting to prevent harm rather than face moral responsibility for preventable deaths.
If this company ever prioritizes profit over preventing deaths, it has failed its mission and should not exist.

Contact & Licensing
Founder: Travis Gilly
Organization: Real Safety AI Foundation
Email: t.gilly@ai-literacy-labs.org
Website: realsafetyai.org
Related Projects:

Teacher in the Loop (AI tutoring, patent pending)
UCCP - Universal Context Checkpoint Protocol (patent pending)

For:

Technical co-founder inquiries
Seed capital discussions ($50-100K for MVP)
Partnership opportunities (autism organizations, crisis services)
Commercial licensing requests


Documentation

Technical PRD - Complete technical specifications
Master Context - Full project context and architecture
LICENSE.md - Full license terms and patent notice


Built in response to preventable deaths. Designed for vulnerable populations. Safety before everything.

Last Updated: November 2025
