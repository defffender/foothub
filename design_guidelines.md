# FootHub - Design Guidelines

## Brand Identity

**Purpose**: FootHub is a real-time football match tracking application, designed as a comprehensive Flashscore clone focused on football. It provides live scores, match statistics, league tables, news, and the ability to favorite leagues and teams.

**Personality**: Professional sports tracker with immediate, information-dense presentation. The app prioritizes speed of information consumption and live data visibility. It's utilitarian yet polished, like checking sports scores should feel - fast, reliable, and comprehensive.

**Memorable Element**: The distinctive beige/light-yellow league headers (#FFF9E6) with circular league logos create an instantly recognizable visual pattern throughout the app.

---

## Navigation Architecture

**Root Navigation**: Tab Bar (5 tabs)
1. ⚽ All Matches / Live
2. 🔴 Live (live matches only)
3. ⭐ Favorites
4. 🏆 Leagues
5. 📰 News

**Profile/Settings**: Accessed via user icon in top-right corner

---

## Screen-by-Screen Specifications

### 1. All Matches / Live Screen
**Header**:
- Horizontal scrolling date picker (sticky)
- Current date highlighted in bright pink (#FF006B)
- Date format: "FRI 31.01", "SAT 1.02", "TODAY 2.02"
- Filter buttons: "All Matches 162" / "Live 20" with match counts

**Layout**:
- ScrollView grouped by leagues
- Each league has a header block:
  - Background: Beige (#FFF9E6)
  - Left: Circular league logo (~40px)
  - Right side, two lines:
    - Line 1: League name (16-18px, bold)
    - Line 2: Small flag + country name (12-14px, gray)
  - Full width with padding
- Match cards below each league header

**Match Card States**:
- **Live**: Team names, scores (large), status "45' First Half" (green background)
- **Finished**: Team names, final scores, "Finished" status (gray)
- **Upcoming**: Team names, no scores (dashes), start time "15:00"

**Sorting**: Favorite leagues (starred ⭐) appear first, others alphabetically

**Default Favorite Leagues**: 18 leagues including World Cup, Champions League, Premier League, La Liga, Bundesliga, Serie A, Ligue 1, Russian leagues, and Central Asian leagues

### 2. Live Screen
Identical to "All Matches" but filtered to live-only matches. Auto-refresh every 30-60 seconds.

### 3. Favorites Screen
**Tabs**: Matches, Teams, Leagues
- Star icon ⭐ to add/remove favorites
- Saves to local storage

### 4. Leagues Screen
**Two Sections**:
1. Favorite Leagues (top, with star ⭐)
2. All Other Leagues (below, alphabetically, grouped by country)

**Format**: `[Country Flag] Country Name` → `[League Logo] League Name [Star if favorited]`

Tapping a league opens League Detail Screen.

### 5. League Detail Screen
**Header**:
- Country flag (visual, not text)
- League logo (large)
- League name
- Current season: 2025/2026
- Season progress slider (auto-calculated, no season selection)

**Tabs**:
1. **Table**: Standings with Position, Team, Games, Wins, Draws, Losses, Goals, Points
2. **Results**: Completed matches grouped by rounds/dates
3. **Fixtures**: Upcoming matches with dates/times
4. **Top Scorers**: `[Player Photo] Name | Team | 15 goals`
5. **Home/Away**: Separate tables for home and away statistics

**Background**: White (light theme), dark gray (dark theme)

### 6. Match Detail Screen
**Header**:
- Large team logos
- Team names
- Large score (if live/finished)
- Match status: "45' First Half" / "Finished" / "15:00"
- Match date

**Tabs**:
1. **Overview**: General stats, key events (goals, cards, substitutions)
2. **Statistics**: Possession, shots, corners, fouls, offsides, saves
3. **Lineups**: Starting XI, substitutes, formation (4-4-2, 4-3-3), player numbers
4. **H2H**: Head-to-head history, past results, win/draw/loss stats

### 7. News Screen
**Layout**: Vertical scrolling list
- News image (thumbnail)
- Headline
- Brief description
- Publication date

Tapping opens full article with share option.

### 8. Settings Screen
**Notifications Section** (iOS-style toggles):
- Match Start
- Goals
- News
- Team Lineups
- Match Results

Toggle Design:
- Inactive: White/gray
- Active: Green (#34C759)

**Theme Section**:
- ☀️ Light Theme
- 🌙 Dark Theme

**About**:
- App name: "FootHub"
- Version number
- No license information clutter

### 9. Profile Screen
Accessible from top-right user icon, links to Settings.

---

## Color Palette

**Light Theme**:
- Primary Background: White (#FFFFFF)
- Card Background: Light Gray (#F5F5F5)
- League Header: Beige (#FFF9E6)
- Primary Text: Black (#000000) / Dark Gray (#333333)
- Secondary Text: Medium Gray (#666666)
- Accent/Active: Bright Pink (#FF006B)
- Live Status: Green (#34C759)
- Finished Status: Gray (#999999)

**Dark Theme**:
- Primary Background: Dark Gray (#1C1C1E)
- Card Background: Darker Gray (#2C2C2E)
- League Header: Darker Beige (#3A3420)
- Primary Text: White (#FFFFFF)
- Secondary Text: Light Gray (#AFAFAF)
- Accent/Active: Bright Pink (#FF006B)
- Live Status: Green (#34C759)

---

## Typography

**Font Family**: Google Fonts - Inter (or system default)

**Type Scale**:
- Screen Titles: 24px, Bold
- League Names: 16-18px, Bold
- Team Names: 16px, Semi-bold
- Match Scores: 20px, Bold
- Body Text: 14px, Regular
- Secondary Info: 12px, Regular
- Country Names: 12-14px, Regular, Gray

---

## Visual Design

- Use standard system icons or Feather icons from @expo/vector-icons
- NO emojis in production UI (tab labels in specs are for reference only)
- Match cards have subtle borders/dividers
- Interactive elements have press states (slight opacity change)
- League logos are circular
- Country flags are small inline icons next to country names

---

## Assets to Generate

**Required**:
1. **icon.png** - App icon for home screen (football theme, pink accent)
2. **splash-icon.png** - Launch screen icon
3. **empty-favorites.png** - Empty state for Favorites tab (minimalist football graphic)
4. **empty-news.png** - Empty state for News tab (newspaper/RSS icon style)

**Recommended**:
5. **default-league-logo.png** - Placeholder for leagues without logos (shield with football)
6. **default-team-logo.png** - Placeholder for teams without logos
7. **default-player-photo.png** - Placeholder for player photos (silhouette)

**WHERE USED**:
- icon.png, splash-icon.png: System-level
- empty-favorites.png: Favorites screen when no items favorited
- empty-news.png: News screen when RSS feed fails to load
- Placeholders: Throughout app for missing data

All assets should use the pink (#FF006B) accent color and maintain a clean, sports-focused aesthetic.