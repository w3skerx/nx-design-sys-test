# Design System

## AI Instructions

Read this file completely before implementing any UI. This is the single source of truth for all visual design decisions.

**Rules:**
1. Use only tokens, components, and patterns defined here
2. Never hardcode colors, spacing, or typography values
3. When combining components, prefer explicit composition over custom CSS
4. If something is not documented, ask before improvising
5. All implementations must support both light and dark modes

---

## Design Philosophy

This system follows Bauhaus principles: form follows function, geometric clarity, and purposeful minimalism.

**Core tenets:**
- Every element serves a function. Remove anything that doesn't.
- Geometric shapes and clean lines over decoration
- Strong visual hierarchy through size, weight, and space
- Limited, intentional color palette with bold accents
- Typography as a structural element, not decoration

---

## Tokens

Tokens are immutable design values. Reference by name, never by raw value.

### Colors

The palette uses an intense modern blue as the primary accent. All colors have light and dark mode variants.

#### Brand Colors

| Token | Light Mode | Dark Mode | Usage |
|-------|------------|-----------|-------|
| `brand-primary` | #2563EB | #3B82F6 | Primary actions, active states, links |
| `brand-primary-hover` | #1D4ED8 | #60A5FA | Hover state for primary elements |
| `brand-primary-active` | #1E40AF | #2563EB | Pressed/active state |
| `brand-primary-subtle` | #EFF6FF | #1E3A5F | Backgrounds, selected rows, highlights |

#### Neutral Colors

| Token | Light Mode | Dark Mode | Usage |
|-------|------------|-----------|-------|
| `neutral-bg` | #FFFFFF | #0F0F0F | Page background |
| `neutral-surface` | #FFFFFF | #171717 | Cards, panels, modals |
| `neutral-surface-raised` | #F9FAFB | #1F1F1F | Raised surfaces, hover states |
| `neutral-border` | #E5E7EB | #2E2E2E | Borders, dividers |
| `neutral-border-strong` | #D1D5DB | #404040 | Emphasized borders, focus rings |
| `neutral-text-primary` | #111827 | #F9FAFB | Headings, primary text |
| `neutral-text-secondary` | #4B5563 | #9CA3AF | Body text, descriptions |
| `neutral-text-muted` | #9CA3AF | #6B7280 | Captions, placeholders, disabled |
| `neutral-text-inverse` | #FFFFFF | #0F0F0F | Text on colored backgrounds |

#### Semantic Colors

| Token | Light Mode | Dark Mode | Usage |
|-------|------------|-----------|-------|
| `success` | #059669 | #10B981 | Success states, positive metrics |
| `success-subtle` | #ECFDF5 | #064E3B | Success backgrounds |
| `warning` | #D97706 | #F59E0B | Warnings, caution states |
| `warning-subtle` | #FFFBEB | #78350F | Warning backgrounds |
| `error` | #DC2626 | #EF4444 | Errors, destructive actions |
| `error-subtle` | #FEF2F2 | #7F1D1D | Error backgrounds |
| `info` | #2563EB | #3B82F6 | Informational states |
| `info-subtle` | #EFF6FF | #1E3A5F | Info backgrounds |

#### Channel Colors

| Token | Value | Usage |
|-------|-------|-------|
| `channel-phone` | #059669 | Phone/voice calls |
| `channel-video` | #7C3AED | Video calls |
| `channel-sms` | #2563EB | SMS/text messaging |
| `channel-email` | #DC2626 | Email |
| `channel-chat` | #0891B2 | Live chat/webchat |
| `channel-internal` | #4B5563 | Internal team messaging |

#### Presence Colors

| Token | Value | Usage |
|-------|-------|-------|
| `presence-online` | #059669 | Available, online |
| `presence-busy` | #DC2626 | Busy, do not disturb |
| `presence-away` | #F59E0B | Away, idle |
| `presence-offline` | #9CA3AF | Offline, unavailable |

### Spacing

Based on a 4px grid. Use for all margins, padding, and gaps.

| Token | Value | Common Uses |
|-------|-------|-------------|
| `space-0` | 0px | Reset spacing |
| `space-1` | 4px | Inline icon gaps, tight groups |
| `space-2` | 8px | Icon-to-text, compact lists, button padding (sm) |
| `space-3` | 12px | Form field internal padding |
| `space-4` | 16px | Default content gap, card padding (sm), button padding (md) |
| `space-5` | 20px | Card padding (md) |
| `space-6` | 24px | Section gaps, card padding (lg) |
| `space-8` | 32px | Major section breaks |
| `space-10` | 40px | Page section separation |
| `space-12` | 48px | Large section gaps |
| `space-16` | 64px | Hero spacing, major landmarks |

### Typography

Font family: **Space Grotesk** (Google Fonts)

Fallback stack: `'Space Grotesk', system-ui, -apple-system, sans-serif`

| Token | Size | Weight | Line Height | Letter Spacing | Usage |
|-------|------|--------|-------------|----------------|-------|
| `display-xl` | 56px | 700 | 1.0 | -0.02em | Hero headlines |
| `display-lg` | 48px | 700 | 1.05 | -0.02em | Page titles |
| `display-md` | 36px | 600 | 1.1 | -0.01em | Section titles |
| `heading-lg` | 28px | 600 | 1.2 | -0.01em | Card titles, major headings |
| `heading-md` | 22px | 600 | 1.25 | 0 | Subsection headings |
| `heading-sm` | 18px | 600 | 1.3 | 0 | Small headings, labels |
| `body-lg` | 18px | 400 | 1.6 | 0 | Lead paragraphs |
| `body-md` | 16px | 400 | 1.5 | 0 | Default body text |
| `body-sm` | 14px | 400 | 1.5 | 0 | Secondary text, table cells |
| `caption` | 12px | 400 | 1.4 | 0.01em | Timestamps, helper text |
| `overline` | 11px | 600 | 1.3 | 0.08em | Labels, categories (uppercase) |
| `mono` | 14px | 400 | 1.5 | 0 | Code, data, IDs |

### Radius

| Token | Value | Usage |
|-------|-------|-------|
| `radius-none` | 0px | Sharp corners when needed |
| `radius-sm` | 4px | Buttons, badges, inputs |
| `radius-md` | 8px | Cards, dropdowns, modals |
| `radius-lg` | 12px | Large cards, panels |
| `radius-xl` | 16px | Feature cards, hero elements |
| `radius-full` | 9999px | Avatars, pills, circular buttons |

### Shadows

| Token | Light Mode | Dark Mode | Usage |
|-------|------------|-----------|-------|
| `shadow-sm` | 0 1px 2px rgba(0,0,0,0.05) | 0 1px 2px rgba(0,0,0,0.3) | Subtle lift, buttons |
| `shadow-md` | 0 4px 6px rgba(0,0,0,0.07) | 0 4px 6px rgba(0,0,0,0.4) | Cards, dropdowns |
| `shadow-lg` | 0 10px 15px rgba(0,0,0,0.1) | 0 10px 15px rgba(0,0,0,0.5) | Modals, popovers |
| `shadow-xl` | 0 20px 25px rgba(0,0,0,0.15) | 0 20px 25px rgba(0,0,0,0.6) | Dialogs, overlays |

### Borders

| Token | Value |
|-------|-------|
| `border-width-default` | 1px |
| `border-width-thick` | 2px |
| `border-style` | solid |

### Z-Index Scale

| Token | Value | Usage |
|-------|-------|-------|
| `z-base` | 0 | Default content |
| `z-dropdown` | 100 | Dropdowns, popovers |
| `z-sticky` | 200 | Sticky headers |
| `z-overlay` | 300 | Modal backdrops |
| `z-modal` | 400 | Modals, dialogs |
| `z-toast` | 500 | Toast notifications |
| `z-tooltip` | 600 | Tooltips |

### Transitions

| Token | Value | Usage |
|-------|-------|-------|
| `duration-fast` | 100ms | Micro-interactions, hovers |
| `duration-normal` | 200ms | Standard transitions |
| `duration-slow` | 300ms | Complex animations |
| `easing-default` | cubic-bezier(0.4, 0, 0.2, 1) | General purpose |
| `easing-in` | cubic-bezier(0.4, 0, 1, 1) | Enter animations |
| `easing-out` | cubic-bezier(0, 0, 0.2, 1) | Exit animations |

---

## Layout Components

### Stack

Arranges children in a row or column with consistent spacing.

```tsx
<Stack
  direction="vertical" | "horizontal"
  gap={SpacingToken}
  align="start" | "center" | "end" | "stretch" | "baseline"
  justify="start" | "center" | "end" | "between" | "around" | "evenly"
  wrap={boolean}
>
  {children}
</Stack>
```

**Examples:**
- Form fields: `<Stack direction="vertical" gap="space-4">`
- Button group: `<Stack direction="horizontal" gap="space-2">`
- Centered content: `<Stack direction="vertical" align="center" justify="center">`

### Grid

CSS Grid-based layout for complex arrangements.

```tsx
<Grid
  columns={1 | 2 | 3 | 4 | 6 | 12}
  gap={SpacingToken}
  columnGap={SpacingToken}
  rowGap={SpacingToken}
>
  {children}
</Grid>
```

**Responsive columns:**
```tsx
<Grid columns={{ base: 1, sm: 2, md: 3, lg: 4 }} gap="space-6">
```

### Container

Centers content with max-width constraints.

```tsx
<Container size="xs" | "sm" | "md" | "lg" | "xl" | "full">
  {children}
</Container>
```

| Size | Max Width |
|------|-----------|
| `xs` | 512px |
| `sm` | 640px |
| `md` | 768px |
| `lg` | 1024px |
| `xl` | 1280px |
| `full` | 100% |

### Section

Semantic page section with consistent vertical spacing.

```tsx
<Section padding="sm" | "md" | "lg" | "xl">
  {children}
</Section>
```

| Size | Padding |
|------|---------|
| `sm` | space-6 |
| `md` | space-10 |
| `lg` | space-12 |
| `xl` | space-16 |

### Divider

Visual separator between content.

```tsx
<Divider 
  orientation="horizontal" | "vertical" 
  spacing={SpacingToken}
  color="default" | "subtle" | "strong"
/>
```

---

## Core Components

### Button

```tsx
<Button
  variant="primary" | "secondary" | "ghost" | "danger" | "success"
  size="sm" | "md" | "lg"
  disabled={boolean}
  loading={boolean}
  fullWidth={boolean}
  leftIcon={IconName}
  rightIcon={IconName}
  onClick={() => void}
>
  {label}
</Button>
```

**Sizing:**
| Size | Height | Padding X | Font |
|------|--------|-----------|------|
| `sm` | 32px | space-3 | body-sm |
| `md` | 40px | space-4 | body-md |
| `lg` | 48px | space-5 | body-lg |

**Variant usage:**
- `primary`: Main action per view (one per screen ideally)
- `secondary`: Supporting actions
- `ghost`: Tertiary actions, toolbar buttons
- `danger`: Destructive actions (delete, remove, end call)
- `success`: Positive confirmations (accept call, save)

### IconButton

Circular or square button containing only an icon.

```tsx
<IconButton
  icon={IconName}
  variant="primary" | "secondary" | "ghost" | "danger"
  size="sm" | "md" | "lg"
  label={string}  // Required for accessibility
  onClick={() => void}
/>
```

### Input

```tsx
<Input
  type="text" | "email" | "password" | "number" | "tel" | "url" | "search"
  label={string}
  placeholder={string}
  value={string}
  onChange={(value: string) => void}
  error={string}
  hint={string}
  disabled={boolean}
  required={boolean}
  leftIcon={IconName}
  rightIcon={IconName}
  rightAddon={ReactNode}
/>
```

### Textarea

```tsx
<Textarea
  label={string}
  placeholder={string}
  value={string}
  onChange={(value: string) => void}
  rows={number}
  maxLength={number}
  error={string}
  hint={string}
  disabled={boolean}
  required={boolean}
  resize="none" | "vertical" | "horizontal" | "both"
/>
```

### Select

```tsx
<Select
  label={string}
  options={Array<{ value: string; label: string; disabled?: boolean }>}
  value={string}
  onChange={(value: string) => void}
  placeholder={string}
  error={string}
  disabled={boolean}
  required={boolean}
  searchable={boolean}
/>
```

### MultiSelect

```tsx
<MultiSelect
  label={string}
  options={Array<{ value: string; label: string }>}
  value={string[]}
  onChange={(value: string[]) => void}
  placeholder={string}
  error={string}
  maxSelected={number}
/>
```

### Checkbox

```tsx
<Checkbox
  label={string}
  checked={boolean}
  onChange={(checked: boolean) => void}
  disabled={boolean}
  indeterminate={boolean}
  description={string}
/>
```

### CheckboxGroup

```tsx
<CheckboxGroup
  label={string}
  options={Array<{ value: string; label: string; description?: string }>}
  value={string[]}
  onChange={(value: string[]) => void}
  direction="vertical" | "horizontal"
/>
```

### Radio

```tsx
<RadioGroup
  label={string}
  options={Array<{ value: string; label: string; description?: string }>}
  value={string}
  onChange={(value: string) => void}
  direction="vertical" | "horizontal"
/>
```

### Toggle

```tsx
<Toggle
  label={string}
  checked={boolean}
  onChange={(checked: boolean) => void}
  disabled={boolean}
  size="sm" | "md"
  description={string}
/>
```

### Slider

```tsx
<Slider
  label={string}
  value={number}
  onChange={(value: number) => void}
  min={number}
  max={number}
  step={number}
  showValue={boolean}
/>
```

---

## Data Display Components

### Text

```tsx
<Text
  variant={TypographyToken}
  color="primary" | "secondary" | "muted" | "inverse" | "success" | "warning" | "error" | "brand"
  align="left" | "center" | "right"
  truncate={boolean}
  as="p" | "span" | "label" | "h1" | "h2" | "h3" | "h4" | "h5" | "h6"
>
  {children}
</Text>
```

### Card

```tsx
<Card
  variant="elevated" | "outlined" | "filled" | "ghost"
  padding="none" | "sm" | "md" | "lg"
  radius="md" | "lg"
  interactive={boolean}  // Adds hover state and cursor
  onClick={() => void}
>
  {children}
</Card>
```

### Avatar

```tsx
<Avatar
  src={string}
  name={string}  // Used for initials fallback and alt text
  size="xs" | "sm" | "md" | "lg" | "xl" | "2xl"
  status="online" | "offline" | "busy" | "away"
  shape="circle" | "square"
/>
```

| Size | Dimensions |
|------|------------|
| `xs` | 24px |
| `sm` | 32px |
| `md` | 40px |
| `lg` | 48px |
| `xl` | 64px |
| `2xl` | 96px |

### AvatarGroup

```tsx
<AvatarGroup
  avatars={Array<{ src?: string; name: string }>}
  max={number}
  size="sm" | "md" | "lg"
/>
```

### Badge

```tsx
<Badge
  variant="default" | "primary" | "success" | "warning" | "error" | "outline"
  size="sm" | "md"
  dot={boolean}  // Shows only a colored dot
>
  {label}
</Badge>
```

### Tag

Dismissible label for categories, filters, or selections.

```tsx
<Tag
  variant="default" | "primary" | "success" | "warning" | "error"
  size="sm" | "md"
  onRemove={() => void}
  removable={boolean}
>
  {label}
</Tag>
```

### Icon

```tsx
<Icon
  name={IconName}
  size="xs" | "sm" | "md" | "lg" | "xl"
  color={ColorToken}
/>
```

| Size | Dimensions |
|------|------------|
| `xs` | 12px |
| `sm` | 16px |
| `md` | 20px |
| `lg` | 24px |
| `xl` | 32px |

**Available Icons:**

Navigation: `chevron-up`, `chevron-down`, `chevron-left`, `chevron-right`, `arrow-up`, `arrow-down`, `arrow-left`, `arrow-right`, `menu`, `more-horizontal`, `more-vertical`, `external-link`

Actions: `plus`, `minus`, `x`, `check`, `edit`, `trash`, `copy`, `download`, `upload`, `refresh`, `search`, `filter`, `sort`, `settings`, `share`

Communication: `phone`, `phone-incoming`, `phone-outgoing`, `phone-missed`, `phone-off`, `video`, `video-off`, `mic`, `mic-off`, `headphones`, `message`, `mail`, `send`, `paperclip`, `at-sign`

People: `user`, `users`, `user-plus`, `user-minus`, `user-check`

Status: `info`, `warning`, `error`, `success`, `help`, `bell`, `bell-off`, `eye`, `eye-off`, `lock`, `unlock`

Objects: `calendar`, `clock`, `star`, `star-filled`, `heart`, `heart-filled`, `bookmark`, `flag`, `tag`, `folder`, `file`, `image`, `link`, `hash`, `building`, `briefcase`

Data: `chart-bar`, `chart-line`, `chart-pie`, `trending-up`, `trending-down`, `activity`

### EmptyState

```tsx
<EmptyState
  icon={IconName}
  title={string}
  description={string}
  action={ReactNode}  // Typically a Button
/>
```

### Stat

Single metric display.

```tsx
<Stat
  label={string}
  value={string | number}
  change={number}  // Percentage change, shows trend indicator
  changeLabel={string}
  trend="up" | "down" | "neutral"
  size="sm" | "md" | "lg"
/>
```

---

## Feedback Components

### Alert

```tsx
<Alert
  variant="info" | "success" | "warning" | "error"
  title={string}
  description={string}
  dismissible={boolean}
  onDismiss={() => void}
  action={{ label: string; onClick: () => void }}
/>
```

### Toast

```tsx
toast({
  variant: "info" | "success" | "warning" | "error",
  title: string,
  description?: string,
  duration?: number,  // Default 5000ms, 0 for persistent
  action?: { label: string; onClick: () => void }
})
```

### Progress

```tsx
<Progress
  value={number}  // 0-100
  max={number}
  size="sm" | "md" | "lg"
  variant="default" | "success" | "warning" | "error"
  showLabel={boolean}
/>
```

### Spinner

```tsx
<Spinner size="sm" | "md" | "lg" color="default" | "primary" | "inverse" />
```

### Skeleton

```tsx
<Skeleton 
  variant="text" | "circular" | "rectangular" 
  width={string | number}
  height={string | number}
/>
```

---

## Overlay Components

### Modal

```tsx
<Modal
  isOpen={boolean}
  onClose={() => void}
  title={string}
  description={string}
  size="sm" | "md" | "lg" | "xl" | "full"
  closeOnOverlayClick={boolean}
  closeOnEsc={boolean}
>
  <ModalBody>{content}</ModalBody>
  <ModalFooter>
    <Button variant="secondary" onClick={onClose}>Cancel</Button>
    <Button variant="primary" onClick={onConfirm}>Confirm</Button>
  </ModalFooter>
</Modal>
```

| Size | Width |
|------|-------|
| `sm` | 400px |
| `md` | 560px |
| `lg` | 720px |
| `xl` | 900px |
| `full` | 100vw - 64px |

### Drawer

```tsx
<Drawer
  isOpen={boolean}
  onClose={() => void}
  title={string}
  position="left" | "right"
  size="sm" | "md" | "lg" | "xl"
>
  {content}
</Drawer>
```

| Size | Width |
|------|-------|
| `sm` | 320px |
| `md` | 400px |
| `lg` | 560px |
| `xl` | 720px |

### Dropdown

```tsx
<Dropdown>
  <DropdownTrigger>
    <Button variant="secondary" rightIcon="chevron-down">Options</Button>
  </DropdownTrigger>
  <DropdownMenu align="start" | "center" | "end">
    <DropdownItem onClick={handler} leftIcon={IconName}>Label</DropdownItem>
    <DropdownItem onClick={handler} disabled>Disabled Item</DropdownItem>
    <DropdownDivider />
    <DropdownItem onClick={handler} variant="danger" leftIcon="trash">Delete</DropdownItem>
  </DropdownMenu>
</Dropdown>
```

### Popover

```tsx
<Popover>
  <PopoverTrigger>
    <Button>Open</Button>
  </PopoverTrigger>
  <PopoverContent align="start" | "center" | "end" side="top" | "bottom" | "left" | "right">
    {content}
  </PopoverContent>
</Popover>
```

### Tooltip

```tsx
<Tooltip content={string} position="top" | "bottom" | "left" | "right" delay={number}>
  <TriggerElement />
</Tooltip>
```

### ConfirmDialog

Pre-built modal for destructive action confirmation.

```tsx
<ConfirmDialog
  isOpen={boolean}
  onClose={() => void}
  onConfirm={() => void}
  title={string}
  description={string}
  confirmLabel={string}
  cancelLabel={string}
  variant="danger" | "warning"
  loading={boolean}
/>
```

---

## Navigation Components

### Tabs

```tsx
<Tabs value={string} onChange={(value: string) => void}>
  <TabList>
    <Tab value="tab1">First Tab</Tab>
    <Tab value="tab2" count={5}>With Count</Tab>
    <Tab value="tab3" disabled>Disabled</Tab>
  </TabList>
  <TabPanels>
    <TabPanel value="tab1">{content}</TabPanel>
    <TabPanel value="tab2">{content}</TabPanel>
  </TabPanels>
</Tabs>
```

### SegmentedControl

Toggle between mutually exclusive options.

```tsx
<SegmentedControl
  value={string}
  onChange={(value: string) => void}
  options={Array<{ value: string; label: string; icon?: IconName }>}
  size="sm" | "md"
/>
```

### Breadcrumb

```tsx
<Breadcrumb>
  <BreadcrumbItem href="/home">Home</BreadcrumbItem>
  <BreadcrumbItem href="/contacts">Contacts</BreadcrumbItem>
  <BreadcrumbItem current>John Doe</BreadcrumbItem>
</Breadcrumb>
```

### Pagination

```tsx
<Pagination
  currentPage={number}
  totalPages={number}
  onPageChange={(page: number) => void}
  showFirstLast={boolean}
  siblingsCount={number}
/>
```

### Sidebar

```tsx
<Sidebar collapsed={boolean} onCollapse={(collapsed: boolean) => void}>
  <SidebarHeader>{logo}</SidebarHeader>
  <SidebarNav>
    <SidebarItem icon="home" href="/dashboard" active>Dashboard</SidebarItem>
    <SidebarItem icon="message" href="/conversations" badge={12}>Conversations</SidebarItem>
    <SidebarGroup label="CRM">
      <SidebarItem icon="users" href="/contacts">Contacts</SidebarItem>
      <SidebarItem icon="building" href="/companies">Companies</SidebarItem>
      <SidebarItem icon="briefcase" href="/deals">Deals</SidebarItem>
    </SidebarGroup>
    <SidebarGroup label="Analytics">
      <SidebarItem icon="chart-bar" href="/reports">Reports</SidebarItem>
    </SidebarGroup>
  </SidebarNav>
  <SidebarFooter>{userMenu}</SidebarFooter>
</Sidebar>
```

---

## Table Components

### Table

Basic table for simple data display.

```tsx
<Table>
  <TableHeader>
    <TableRow>
      <TableHead>Name</TableHead>
      <TableHead sortable sorted="asc" onSort={handler}>Email</TableHead>
      <TableHead align="right">Actions</TableHead>
    </TableRow>
  </TableHeader>
  <TableBody>
    <TableRow>
      <TableCell>John Doe</TableCell>
      <TableCell>john@example.com</TableCell>
      <TableCell align="right">
        <Button variant="ghost" size="sm">Edit</Button>
      </TableCell>
    </TableRow>
  </TableBody>
</Table>
```

### DataTable

Full-featured table with sorting, filtering, selection, and pagination.

```tsx
<DataTable
  data={Array<object>}
  columns={Array<{
    key: string;
    header: string;
    sortable?: boolean;
    width?: string;
    align?: "left" | "center" | "right";
    render?: (value: any, row: object) => ReactNode;
  }>}
  selectable={boolean}
  selectedRows={string[]}
  onSelectionChange={(ids: string[]) => void}
  sortBy={string}
  sortDirection="asc" | "desc"
  onSort={(key: string) => void}
  pagination={{
    currentPage: number;
    totalPages: number;
    pageSize: number;
    onPageChange: (page: number) => void;
  }}
  loading={boolean}
  emptyState={ReactNode}
  onRowClick={(row: object) => void}
/>
```

---

## Communication Components

### ChannelIcon

Displays the appropriate icon for a communication channel.

```tsx
<ChannelIcon
  channel="phone" | "video" | "sms" | "email" | "chat" | "internal"
  size="sm" | "md" | "lg"
/>
```

### PresenceIndicator

Shows user availability status.

```tsx
<PresenceIndicator
  status="online" | "offline" | "busy" | "away"
  size="sm" | "md"
  pulse={boolean}  // Animated pulse for active states
/>
```

### MessageBubble

Single message in a conversation thread.

```tsx
<MessageBubble
  content={string}
  timestamp={Date}
  sender="self" | "other" | "system"
  status="sending" | "sent" | "delivered" | "read" | "error"
  attachments={Array<{ type: string; url: string; name: string }>}
/>
```

### ConversationThread

Container for a series of messages.

```tsx
<ConversationThread
  messages={Array<Message>}
  loading={boolean}
  onLoadMore={() => void}
  hasMore={boolean}
>
  {messages.map(msg => <MessageBubble key={msg.id} {...msg} />)}
</ConversationThread>
```

### ConversationPreview

List item showing conversation summary.

```tsx
<ConversationPreview
  contact={{ name: string; avatar?: string }}
  channel="phone" | "video" | "sms" | "email" | "chat"
  lastMessage={string}
  timestamp={Date}
  unreadCount={number}
  status="active" | "waiting" | "closed"
  onClick={() => void}
  selected={boolean}
/>
```

### TypingIndicator

Shows when someone is typing.

```tsx
<TypingIndicator names={string[]} />
```

### CallControls

Action bar for active calls.

```tsx
<CallControls
  callType="voice" | "video"
  isMuted={boolean}
  onMuteToggle={() => void}
  isVideoOff={boolean}
  onVideoToggle={() => void}
  isOnHold={boolean}
  onHoldToggle={() => void}
  onTransfer={() => void}
  onEnd={() => void}
  duration={number}  // Seconds, displays formatted time
/>
```

### CallStatus

Displays current call state.

```tsx
<CallStatus
  status="ringing" | "connecting" | "active" | "on-hold" | "ended"
  direction="inbound" | "outbound"
  duration={number}
  contact={{ name: string; avatar?: string; number?: string }}
/>
```

### Dialpad

Numeric keypad for phone input.

```tsx
<Dialpad
  value={string}
  onChange={(value: string) => void}
  onCall={() => void}
  onBackspace={() => void}
/>
```

---

## CRM Components

### ContactCard

Compact contact display for lists or embeds.

```tsx
<ContactCard
  contact={{
    id: string;
    name: string;
    avatar?: string;
    email?: string;
    phone?: string;
    company?: string;
    title?: string;
    status?: "active" | "inactive";
    tags?: string[];
  }}
  variant="compact" | "expanded"
  onClick={() => void}
  actions={ReactNode}
/>
```

### CompanyCard

Company/account display.

```tsx
<CompanyCard
  company={{
    id: string;
    name: string;
    logo?: string;
    industry?: string;
    size?: string;
    website?: string;
    contactCount?: number;
    dealValue?: number;
  }}
  variant="compact" | "expanded"
  onClick={() => void}
/>
```

### DealCard

Opportunity/deal display.

```tsx
<DealCard
  deal={{
    id: string;
    name: string;
    value: number;
    currency: string;
    stage: string;
    probability: number;
    closeDate?: Date;
    contact?: { name: string; avatar?: string };
    company?: { name: string; logo?: string };
  }}
  onClick={() => void}
/>
```

### Pipeline

Visual pipeline/kanban view.

```tsx
<Pipeline
  stages={Array<{ id: string; name: string; color?: string }>}
  deals={Array<Deal>}
  onDealMove={(dealId: string, stageId: string) => void}
  onDealClick={(deal: Deal) => void}
  showValues={boolean}
/>
```

### ActivityTimeline

Chronological list of activities and events.

```tsx
<ActivityTimeline>
  <ActivityItem
    type="call" | "email" | "meeting" | "note" | "task" | "deal" | "status-change"
    title={string}
    description={string}
    timestamp={Date}
    user={{ name: string; avatar?: string }}
    icon={IconName}
  />
</ActivityTimeline>
```

### TaskList

List of tasks with completion states.

```tsx
<TaskList
  tasks={Array<{
    id: string;
    title: string;
    dueDate?: Date;
    priority: "low" | "medium" | "high";
    completed: boolean;
    assignee?: { name: string; avatar?: string };
  }>}
  onTaskToggle={(id: string, completed: boolean) => void}
  onTaskClick={(task: Task) => void}
/>
```

### NoteEditor

Rich text editor for notes.

```tsx
<NoteEditor
  value={string}
  onChange={(value: string) => void}
  placeholder={string}
  mentions={Array<{ id: string; name: string }>}  // For @mentions
  onMention={(userId: string) => void}
  autosave={boolean}
  lastSaved={Date}
/>
```

### ContactField

Display field for contact properties with inline editing.

```tsx
<ContactField
  label={string}
  value={string | string[]}
  type="text" | "email" | "phone" | "url" | "date" | "select" | "multi-select"
  editable={boolean}
  onSave={(value: string) => void}
  options={Array<{ value: string; label: string }>}  // For select types
/>
```

---

## Analytics Components

### MetricCard

Single KPI with optional trend indicator.

```tsx
<MetricCard
  title={string}
  value={string | number}
  change={number}
  changeLabel={string}
  trend="up" | "down" | "neutral"
  icon={IconName}
  sparkline={Array<number>}
  loading={boolean}
  onClick={() => void}
/>
```

### Chart

Wrapper for data visualization.

```tsx
<Chart
  type="bar" | "line" | "area" | "pie" | "donut"
  data={{
    labels: string[];
    datasets: Array<{
      label: string;
      data: number[];
      color?: string;
    }>;
  }}
  height={number}
  showLegend={boolean}
  showGrid={boolean}
  showTooltip={boolean}
  animate={boolean}
/>
```

### Sparkline

Inline mini chart for trends.

```tsx
<Sparkline
  data={Array<number>}
  width={number}
  height={number}
  color="default" | "success" | "warning" | "error"
  showEndpoint={boolean}
/>
```

### ProgressRing

Circular progress indicator with percentage.

```tsx
<ProgressRing
  value={number}
  max={number}
  size="sm" | "md" | "lg"
  color="default" | "success" | "warning" | "error"
  showLabel={boolean}
/>
```

### FilterBar

Toolbar for filtering data views.

```tsx
<FilterBar>
  <FilterGroup label="Date">
    <DateRangePicker value={dateRange} onChange={setDateRange} />
  </FilterGroup>
  <FilterGroup label="Channel">
    <MultiSelect options={channels} value={selectedChannels} onChange={setSelectedChannels} />
  </FilterGroup>
  <FilterGroup label="Agent">
    <Select options={agents} value={selectedAgent} onChange={setSelectedAgent} />
  </FilterGroup>
  <FilterBarActions>
    <Button variant="ghost" onClick={clearFilters}>Clear All</Button>
  </FilterBarActions>
</FilterBar>
```

### DateRangePicker

Date range selection with presets.

```tsx
<DateRangePicker
  value={{ start: Date; end: Date }}
  onChange={(range: { start: Date; end: Date }) => void}
  presets={Array<{ label: string; start: Date; end: Date }>}
  minDate={Date}
  maxDate={Date}
/>
```

**Default presets:** Today, Yesterday, Last 7 days, Last 30 days, This month, Last month, Custom range

### Leaderboard

Ranked list of items with values.

```tsx
<Leaderboard
  title={string}
  items={Array<{
    rank: number;
    name: string;
    avatar?: string;
    value: number;
    change?: number;
  }>}
  valueLabel={string}
  showChange={boolean}
/>
```

---

## Form Patterns

### Standard Form Layout

```tsx
<form>
  <Stack direction="vertical" gap="space-6">
    <Stack direction="vertical" gap="space-4">
      <Input label="First Name" required />
      <Input label="Last Name" required />
      <Input label="Email" type="email" required />
      <Select label="Role" options={roles} />
      <Textarea label="Notes" rows={4} />
    </Stack>
    
    <Divider />
    
    <Stack direction="horizontal" gap="space-3" justify="end">
      <Button variant="secondary">Cancel</Button>
      <Button variant="primary" type="submit">Save Contact</Button>
    </Stack>
  </Stack>
</form>
```

### Two-Column Form

```tsx
<form>
  <Grid columns={{ base: 1, md: 2 }} gap="space-4">
    <Input label="First Name" />
    <Input label="Last Name" />
    <Input label="Email" type="email" />
    <Input label="Phone" type="tel" />
    <div className="col-span-full">
      <Textarea label="Address" />
    </div>
  </Grid>
</form>
```

### Settings Form

```tsx
<Stack direction="vertical" gap="space-8">
  <Section>
    <Stack direction="vertical" gap="space-4">
      <Text variant="heading-md">Notifications</Text>
      <Toggle label="Email notifications" description="Receive email for new messages" />
      <Toggle label="Push notifications" description="Receive push for urgent items" />
      <Toggle label="Weekly digest" description="Summary of activity each week" />
    </Stack>
  </Section>
  
  <Divider />
  
  <Section>
    <Stack direction="vertical" gap="space-4">
      <Text variant="heading-md">Privacy</Text>
      <RadioGroup
        label="Profile visibility"
        options={[
          { value: "public", label: "Public", description: "Anyone can see your profile" },
          { value: "team", label: "Team only", description: "Only team members" },
          { value: "private", label: "Private", description: "Only you" }
        ]}
      />
    </Stack>
  </Section>
</Stack>
```

---

## Page Patterns

### Page Header

```tsx
<Stack direction="vertical" gap="space-2">
  <Breadcrumb>
    <BreadcrumbItem href="/contacts">Contacts</BreadcrumbItem>
    <BreadcrumbItem current>John Doe</BreadcrumbItem>
  </Breadcrumb>
  
  <Stack direction="horizontal" justify="between" align="center">
    <Stack direction="horizontal" gap="space-4" align="center">
      <Avatar name="John Doe" size="xl" />
      <Stack direction="vertical" gap="space-0">
        <Text variant="display-md">John Doe</Text>
        <Text variant="body-md" color="secondary">Product Manager at Acme Corp</Text>
      </Stack>
    </Stack>
    
    <Stack direction="horizontal" gap="space-2">
      <Button variant="secondary" leftIcon="mail">Email</Button>
      <Button variant="primary" leftIcon="phone">Call</Button>
      <Dropdown>
        <DropdownTrigger>
          <IconButton icon="more-horizontal" variant="ghost" label="More actions" />
        </DropdownTrigger>
        <DropdownMenu>
          <DropdownItem leftIcon="edit">Edit</DropdownItem>
          <DropdownItem leftIcon="trash" variant="danger">Delete</DropdownItem>
        </DropdownMenu>
      </Dropdown>
    </Stack>
  </Stack>
</Stack>
```

### Dashboard Layout

```tsx
<Stack direction="vertical" gap="space-6">
  <Stack direction="horizontal" justify="between" align="center">
    <Text variant="display-md">Dashboard</Text>
    <DateRangePicker value={dateRange} onChange={setDateRange} />
  </Stack>
  
  <Grid columns={{ base: 1, sm: 2, lg: 4 }} gap="space-4">
    <MetricCard title="Total Calls" value={1234} change={12} trend="up" icon="phone" />
    <MetricCard title="Avg Duration" value="4:32" change={-5} trend="down" icon="clock" />
    <MetricCard title="Deals Won" value={23} change={8} trend="up" icon="briefcase" />
    <MetricCard title="Revenue" value="$45,678" change={15} trend="up" icon="trending-up" />
  </Grid>
  
  <Grid columns={{ base: 1, lg: 2 }} gap="space-6">
    <Card padding="md">
      <Stack direction="vertical" gap="space-4">
        <Text variant="heading-md">Call Volume</Text>
        <Chart type="area" data={callVolumeData} height={300} />
      </Stack>
    </Card>
    
    <Card padding="md">
      <Stack direction="vertical" gap="space-4">
        <Text variant="heading-md">Top Performers</Text>
        <Leaderboard items={topPerformers} valueLabel="calls" />
      </Stack>
    </Card>
  </Grid>
</Stack>
```

### List View

```tsx
<Stack direction="vertical" gap="space-4">
  <Stack direction="horizontal" justify="between" align="center">
    <Text variant="heading-lg">Contacts</Text>
    <Button variant="primary" leftIcon="plus">Add Contact</Button>
  </Stack>
  
  <FilterBar>
    <Input placeholder="Search contacts..." leftIcon="search" />
    <MultiSelect options={tags} value={selectedTags} onChange={setSelectedTags} placeholder="Tags" />
    <Select options={sortOptions} value={sortBy} onChange={setSortBy} placeholder="Sort by" />
  </FilterBar>
  
  <DataTable
    data={contacts}
    columns={columns}
    selectable
    selectedRows={selected}
    onSelectionChange={setSelected}
    pagination={pagination}
    onRowClick={handleRowClick}
  />
</Stack>
```

### Detail View (Split)

```tsx
<Grid columns={{ base: 1, lg: "2fr 1fr" }} gap="space-6">
  <Stack direction="vertical" gap="space-6">
    <Card padding="md">
      <Tabs value={activeTab} onChange={setActiveTab}>
        <TabList>
          <Tab value="activity">Activity</Tab>
          <Tab value="notes">Notes</Tab>
          <Tab value="tasks">Tasks</Tab>
          <Tab value="deals">Deals</Tab>
        </TabList>
        <TabPanels>
          <TabPanel value="activity">
            <ActivityTimeline>{activities}</ActivityTimeline>
          </TabPanel>
          <TabPanel value="notes">
            <NoteEditor value={note} onChange={setNote} />
          </TabPanel>
          <TabPanel value="tasks">
            <TaskList tasks={tasks} onTaskToggle={handleToggle} />
          </TabPanel>
          <TabPanel value="deals">
            <Stack direction="vertical" gap="space-3">
              {deals.map(deal => <DealCard key={deal.id} deal={deal} />)}
            </Stack>
          </TabPanel>
        </TabPanels>
      </Tabs>
    </Card>
  </Stack>
  
  <Stack direction="vertical" gap="space-4">
    <Card padding="md">
      <Stack direction="vertical" gap="space-4">
        <Text variant="heading-sm">Contact Details</Text>
        <ContactField label="Email" value={contact.email} type="email" editable />
        <ContactField label="Phone" value={contact.phone} type="phone" editable />
        <ContactField label="Company" value={contact.company} type="text" editable />
        <ContactField label="Title" value={contact.title} type="text" editable />
        <ContactField label="Tags" value={contact.tags} type="multi-select" editable options={allTags} />
      </Stack>
    </Card>
    
    <Card padding="md">
      <Stack direction="vertical" gap="space-3">
        <Text variant="heading-sm">Recent Conversations</Text>
        {conversations.map(conv => (
          <ConversationPreview key={conv.id} {...conv} />
        ))}
      </Stack>
    </Card>
  </Stack>
</Grid>
```

---

## Accessibility Requirements

Every implementation must meet these requirements:

1. **Focus visibility**: All interactive elements show a visible focus ring using `brand-primary` color, 2px width, 2px offset

2. **Color independence**: Never convey information by color alone. Pair with icons, text, or patterns.

3. **Touch targets**: Minimum 44x44px for all interactive elements on touch devices

4. **Labels**: Every form input has an associated `<label>`. Use `aria-label` for icon-only buttons.

5. **Alt text**: Images require descriptive alt text. Decorative images use `alt=""`

6. **Keyboard navigation**: All functionality accessible via keyboard. Logical tab order.

7. **Heading hierarchy**: Use heading levels in order (h1 → h2 → h3). Never skip levels.

8. **ARIA states**: Use `aria-expanded`, `aria-selected`, `aria-disabled`, `aria-live` appropriately

9. **Reduced motion**: Respect `prefers-reduced-motion` media query. Disable animations when set.

10. **Contrast ratios**: Text meets WCAG AA (4.5:1 for normal text, 3:1 for large text)

---

## Responsive Breakpoints

| Token | Value | Target |
|-------|-------|--------|
| `sm` | 640px | Large phones |
| `md` | 768px | Tablets |
| `lg` | 1024px | Small laptops |
| `xl` | 1280px | Desktops |
| `2xl` | 1536px | Large screens |

**Mobile-first approach**: Base styles target mobile. Add complexity at larger breakpoints.

```tsx
// Example responsive pattern
<Grid columns={{ base: 1, md: 2, lg: 3 }} gap="space-6">
  {cards}
</Grid>

// Example responsive visibility
<div className="hidden md:block">{desktopOnly}</div>
<div className="md:hidden">{mobileOnly}</div>
```

---

## Guidance for Common Scenarios

**Q: What if I need a component not listed here?**
Compose from existing primitives (Stack, Card, Text, Button). If that's insufficient, ask before creating a custom solution.

**Q: How do I handle loading states?**
Use `Skeleton` components that match the shape of the content being loaded. For buttons and forms, use the `loading` prop.

**Q: How do I handle empty states?**
Use the `EmptyState` component with a relevant icon, clear title, helpful description, and action button when applicable.

**Q: How do I handle errors in forms?**
Use the `error` prop on form fields. Display inline errors below the field, not in toasts or alerts.

**Q: When should I use a Modal vs a Drawer?**
Modal for focused tasks requiring immediate attention (confirmations, small forms). Drawer for secondary content that doesn't interrupt flow (details panels, extended forms).

**Q: How do I maintain consistency in dark mode?**
Always use semantic color tokens, never raw hex values. The tokens automatically adapt to the color mode.
