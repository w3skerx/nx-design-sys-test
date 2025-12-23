# Design System

Read this file completely before implementing any UI. This defines the visual language—use these tokens and components exactly as specified.

## Style Direction

Bauhaus-inspired minimal design. Geometric forms, functional clarity, no decoration for decoration's sake. Bold use of primary blue against neutral backgrounds. Clean lines, generous whitespace, confident typography. The interface should feel precise, modern, and quietly powerful.

## Tokens

### Colors

```
primary-50: #EBF5FF
primary-100: #D6EBFF
primary-200: #ADD6FF
primary-300: #85C2FF
primary-400: #5CADFF
primary-500: #0066FF   ← primary brand color
primary-600: #0052CC
primary-700: #003D99
primary-800: #002966
primary-900: #001433

neutral-0: #FFFFFF
neutral-50: #FAFAFA
neutral-100: #F5F5F5
neutral-200: #E5E5E5
neutral-300: #D4D4D4
neutral-400: #A3A3A3
neutral-500: #737373
neutral-600: #525252
neutral-700: #404040
neutral-800: #262626
neutral-900: #171717
neutral-950: #0A0A0A

success-500: #10B981
success-600: #059669

warning-500: #F59E0B
warning-600: #D97706

error-500: #EF4444
error-600: #DC2626

info-500: #3B82F6
info-600: #2563EB
```

### Dark Mode Colors

In dark mode, surfaces invert but the primary blue remains constant:

```
surface-primary: neutral-900
surface-secondary: neutral-800
surface-elevated: neutral-800
border-default: neutral-700
text-primary: neutral-50
text-secondary: neutral-400
text-tertiary: neutral-500
```

### Typography

Font family: `"Space Grotesk", sans-serif`

```
text-xs: 12px / 16px
text-sm: 14px / 20px
text-base: 16px / 24px
text-lg: 18px / 28px
text-xl: 20px / 28px
text-2xl: 24px / 32px
text-3xl: 30px / 36px
text-4xl: 36px / 40px
```

Font weights: `400` (regular), `500` (medium), `700` (bold)

Use medium (500) for UI labels and buttons. Use bold (700) sparingly—headings and emphasis only.

### Spacing

Base unit: 4px. Use only these values:

```
spacing-0: 0
spacing-1: 4px
spacing-2: 8px
spacing-3: 12px
spacing-4: 16px
spacing-5: 20px
spacing-6: 24px
spacing-8: 32px
spacing-10: 40px
spacing-12: 48px
spacing-16: 64px
spacing-20: 80px
spacing-24: 96px
```

### Radius

```
radius-none: 0
radius-sm: 4px
radius-md: 8px
radius-lg: 12px
radius-xl: 16px
radius-full: 9999px
```

Bauhaus preference: favor `radius-sm` and `radius-md`. Use `radius-full` only for avatars and circular buttons.

### Shadows

```
shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05)
shadow-md: 0 4px 6px rgba(0, 0, 0, 0.07), 0 2px 4px rgba(0, 0, 0, 0.05)
shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1), 0 4px 6px rgba(0, 0, 0, 0.05)
shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.1), 0 10px 10px rgba(0, 0, 0, 0.04)
```

Use shadows sparingly. Prefer border separation over shadow separation.

### Breakpoints

```
sm: 640px
md: 768px
lg: 1024px
xl: 1280px
2xl: 1536px
```

Desktop-first. Design for `lg` and above, then adapt down.

## Icons

Use Lucide React exclusively.

```tsx
import { Phone, Mail, MessageSquare, Video, Users, Building2, TrendingUp } from 'lucide-react'
```

Default size: 20px for UI, 16px for inline with text, 24px for emphasis.

Stroke width: Use default (2). Do not modify.

## Component APIs

Components are the allowed building blocks. Use only the variants and props defined here.

### Button

```tsx
<Button
  variant="primary" | "secondary" | "ghost" | "danger"
  size="sm" | "md" | "lg"
  disabled?: boolean
  loading?: boolean
  icon?: LucideIcon
  iconPosition?: "left" | "right"
/>
```

Primary buttons use `primary-500` background. One primary button per view.

### IconButton

```tsx
<IconButton
  icon={LucideIcon}
  variant="primary" | "secondary" | "ghost" | "danger"
  size="sm" | "md" | "lg"
  label: string  // required for accessibility
/>
```

### Input

```tsx
<Input
  type="text" | "email" | "password" | "tel" | "number" | "search"
  size="sm" | "md" | "lg"
  placeholder?: string
  disabled?: boolean
  error?: boolean
  helperText?: string
  icon?: LucideIcon
/>
```

### Textarea

```tsx
<Textarea
  rows?: number
  placeholder?: string
  disabled?: boolean
  error?: boolean
  resize?: "none" | "vertical" | "horizontal"
/>
```

### Select

```tsx
<Select
  options={Array<{ value: string, label: string }>}
  placeholder?: string
  disabled?: boolean
  error?: boolean
  size="sm" | "md" | "lg"
/>
```

### Checkbox

```tsx
<Checkbox
  checked?: boolean
  indeterminate?: boolean
  disabled?: boolean
  label?: string
/>
```

### Radio

```tsx
<Radio
  checked?: boolean
  disabled?: boolean
  label?: string
/>
```

### RadioGroup

```tsx
<RadioGroup
  options={Array<{ value: string, label: string }>}
  value?: string
  orientation="horizontal" | "vertical"
/>
```

### Toggle

```tsx
<Toggle
  checked?: boolean
  disabled?: boolean
  size="sm" | "md"
/>
```

### Avatar

```tsx
<Avatar
  src?: string
  name: string  // used for fallback initials
  size="xs" | "sm" | "md" | "lg" | "xl"
  status?: "online" | "offline" | "busy" | "away"
/>
```

### AvatarGroup

```tsx
<AvatarGroup
  avatars={Array<{ src?: string, name: string }>}
  max?: number  // shows +N overflow
  size="sm" | "md" | "lg"
/>
```

### Badge

```tsx
<Badge
  variant="neutral" | "primary" | "success" | "warning" | "error"
  size="sm" | "md"
/>
```

### Tag

```tsx
<Tag
  variant="neutral" | "primary" | "success" | "warning" | "error"
  removable?: boolean
  onRemove?: () => void
/>
```

### Tooltip

```tsx
<Tooltip
  content: string
  position="top" | "bottom" | "left" | "right"
  delay?: number
/>
```

### Card

```tsx
<Card
  padding="none" | "sm" | "md" | "lg"
  border?: boolean
  shadow?: boolean
  interactive?: boolean  // adds hover state
/>
```

### Modal

```tsx
<Modal
  open: boolean
  onClose: () => void
  size="sm" | "md" | "lg" | "xl"
  title?: string
  description?: string
/>
```

### Drawer

```tsx
<Drawer
  open: boolean
  onClose: () => void
  position="left" | "right"
  size="sm" | "md" | "lg"
  title?: string
/>
```

### Dropdown

```tsx
<Dropdown
  trigger: ReactNode
  align="start" | "center" | "end"
/>

<DropdownItem
  icon?: LucideIcon
  destructive?: boolean
  disabled?: boolean
/>

<DropdownSeparator />
```

### Tabs

```tsx
<Tabs
  defaultValue: string
  orientation="horizontal" | "vertical"
/>

<TabsList />
<TabsTrigger value: string />
<TabsContent value: string />
```

### Table

```tsx
<Table>
  <TableHeader>
    <TableRow>
      <TableHead sortable?: boolean />
    </TableRow>
  </TableHeader>
  <TableBody>
    <TableRow selectable?: boolean selected?: boolean>
      <TableCell />
    </TableRow>
  </TableBody>
</Table>
```

### EmptyState

```tsx
<EmptyState
  icon?: LucideIcon
  title: string
  description?: string
  action?: ReactNode
/>
```

### Spinner

```tsx
<Spinner
  size="sm" | "md" | "lg"
/>
```

### Skeleton

```tsx
<Skeleton
  width?: string | number
  height?: string | number
  variant="text" | "circular" | "rectangular"
/>
```

### Toast

```tsx
toast({
  variant: "neutral" | "success" | "warning" | "error"
  title: string
  description?: string
  duration?: number
})
```

### Alert

```tsx
<Alert
  variant="info" | "success" | "warning" | "error"
  title?: string
  dismissible?: boolean
/>
```

### Divider

```tsx
<Divider
  orientation="horizontal" | "vertical"
  spacing="sm" | "md" | "lg"
/>
```

### StatusIndicator

```tsx
<StatusIndicator
  status="online" | "offline" | "busy" | "away" | "dnd"
  size="sm" | "md"
  pulse?: boolean
/>
```

## Layout

### Stack

```tsx
<Stack
  direction="horizontal" | "vertical"
  gap="spacing token"
  align="start" | "center" | "end" | "stretch"
  justify="start" | "center" | "end" | "between"
/>
```

### Grid

Use CSS Grid or Tailwind grid utilities. Prefer 12-column grid for page layouts.

### Container

```tsx
<Container
  maxWidth="sm" | "md" | "lg" | "xl" | "2xl" | "full"
  padding?: boolean  // adds horizontal padding
/>
```

## Constraints

These are non-negotiable:

1. **Spacing**: Use only defined spacing tokens. No arbitrary pixel values.

2. **Color**: Use only defined color tokens. No hex codes outside the system.

3. **Typography**: Space Grotesk only. Use defined size scale.

4. **Icons**: Lucide only. No mixing icon libraries.

5. **Radius**: Prefer small radii (sm, md). Reserve full radius for avatars and pills.

6. **Accessibility**: 
   - All interactive elements must be keyboard accessible
   - Minimum touch target: 44x44px on mobile
   - Color contrast: WCAG AA minimum (4.5:1 for text, 3:1 for UI)
   - Always provide aria-labels for icon-only buttons
   - Focus states must be visible

7. **Motion**: Keep transitions under 200ms. Use ease-out for enters, ease-in for exits.

8. **Density**: Generous whitespace. When in doubt, add more space.

## When Uncertain

If a design decision isn't covered here:

1. Follow Bauhaus principles: function dictates form, no unnecessary elements
2. Match the minimal, geometric aesthetic established by existing components
3. When in doubt, simpler is better
4. Ask for guidance rather than inventing new patterns
