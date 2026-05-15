# Nâng Cấp Không Gian Làm Việc — 2 Sub-Agents & Skills

Dự án này xây dựng 2 Claude Code sub-agents chuyên biệt, mỗi agent được trang bị bộ SKILLS riêng, và kết quả thực chiến từ việc 2 agent phối hợp tạo ra kế hoạch marketing hoàn chỉnh cho khóa học tiếng Anh giao tiếp.

---

## Cấu trúc

```
├── agents/                           # Sub-agent definitions (.claude/agents/)
│   ├── content-social-media.md       # Agent chuyên Content Social Media
│   └── technical-facebook-ads.md     # Agent chuyên Facebook Ads kỹ thuật
│
├── skills/                           # Skill files cho từng agent (.claude/skills/)
│   ├── content-social-media/
│   │   ├── hooks.md                  # 7 loại hook + công thức viết
│   │   ├── copywriting-frameworks.md # AIDA, PAS, BAB, FAB, PASTOR, 4U
│   │   ├── platform-guidelines.md    # Facebook, Instagram, TikTok, LinkedIn
│   │   └── content-strategy.md      # Content pillars, calendar, KPIs
│   │
│   └── facebook-ads/
│       ├── meta-ads.md               # Campaign structure, audience, bidding
│       ├── tracking-setup.md         # Pixel, CAPI, GTM, UTM
│       └── campaign-optimization.md  # Diagnose, scale, A/B test, reporting
│
└── outputs/                          # Kết quả thực chiến từ 2 agents
    ├── english-course-content-30days.md     # 30 bài content (POST-01 → POST-30)
    └── english-course-facebook-ads-plan.md  # Kế hoạch Facebook Ads 30 ngày
```

---

## 2 Sub-Agents

### Agent 1: `content-social-media`

**Vai trò:** Senior Content Strategist & Copywriter chuyên Social Media tại thị trường Việt Nam.

**Skills được trang bị:**
- `hooks.md` — 7 loại hook, công thức viết hook theo từng platform
- `copywriting-frameworks.md` — AIDA, PAS, BAB, FAB, PASTOR, 4U Formula + CTA templates
- `platform-guidelines.md` — Đặc thù thuật toán và best practices của Facebook, Instagram, TikTok, LinkedIn
- `content-strategy.md` — Content pillars, content mix 40/30/20/10, lịch content, KPIs, repurposing

---

### Agent 2: `technical-facebook-ads`

**Vai trò:** Senior Facebook Ads Specialist với chuyên môn kỹ thuật Meta Ads cho thị trường Việt Nam.

**Skills được trang bị:**
- `meta-ads.md` — Cấu trúc Campaign→AdSet→Ad, 3-layer audience, bidding strategies, Learning Phase
- `tracking-setup.md` — Meta Pixel, Conversions API (CAPI), GTM, UTM parameters, pre-launch checklist
- `campaign-optimization.md` — Benchmarks thị trường VN, diagnose framework, scaling strategy, A/B testing, reporting

---

## Kết Quả Thực Chiến: Khóa Học Tiếng Anh Giao Tiếp

### Output 1 — Content 30 Ngày

30 bài content hoàn chỉnh (POST-01 → POST-30) theo phễu marketing 3 tầng:

| Phễu | Bài | Mục tiêu | CTA |
|------|-----|----------|-----|
| Lạnh (Cold) | POST-01 → POST-10 | Awareness | Nhẹ: Follow, Save, Share |
| Ấm (Warm) | POST-11 → POST-22 | Consideration | Trung: Comment, Inbox tư vấn |
| Nóng (Hot) | POST-23 → POST-30 | Conversion | Mạnh: Đăng ký, điền form |

Format: 14 bài viết · 6 carousel · 6 video/Reels · 2 ảnh quote · 3 poll

### Output 2 — Kế Hoạch Facebook Ads 30 Ngày

3 Campaigns — 11 Ad Sets — dùng POST-01→POST-30 làm creative:

| Campaign | Objective | Ad Sets | Creative |
|----------|-----------|---------|---------|
| C1 — AWARENESS | Video Views | C1-A1, C1-A2, C1-A3, C1-A4 | POST-01 → POST-10 |
| C2 — CONSIDERATION | Leads | C2-W1, C2-W2, C2-W3, C2-W4 | POST-11 → POST-22 |
| C3 — CONVERSION | Leads (High Intent) | C3-H1, C3-H2, C3-H3 | POST-23 → POST-30 |

**3 mức ngân sách:** 15 triệu / 45 triệu / 90 triệu VND (30 ngày)

**6 phương án tối ưu:** CTR thấp · CPL cao · Underdelivery · Frequency bão hòa · Campaign win · Ads bị reject

---

## Cách cài vào Claude Code

```bash
cp agents/content-social-media.md ~/.claude/agents/
cp agents/technical-facebook-ads.md ~/.claude/agents/
mkdir -p ~/.claude/skills/content-social-media ~/.claude/skills/facebook-ads
cp skills/content-social-media/* ~/.claude/skills/content-social-media/
cp skills/facebook-ads/* ~/.claude/skills/facebook-ads/
```
