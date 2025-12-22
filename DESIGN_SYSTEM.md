# Nextiva Test Design System

**Version:** 1.0.0  
**Purpose:** Test design system with distinctive, verifiable features

## 🎨 Design Tokens

### Colors

**IMPORTANT:** These are non-standard colors chosen specifically for verification purposes.

```css
/* Primary: Purple (NOT blue) */
--color-primary: #6B4EFF;
--color-primary-hover: #5A3FE6;
--color-primary-active: #4930CC;

/* Secondary: Coral Orange */
--color-secondary: #FF6B4E;
--color-secondary-hover: #E65A3F;
--color-secondary-active: #CC4930;

/* Success: Bright Green */
--color-success: #4EFF6B;
--color-success-hover: #3FE65A;
--color-success-active: #30CC49;

/* Error: Pink-Red */
--color-error: #FF4E6B;
--color-error-hover: #E63F5A;
--color-error-active: #CC3049;

/* Neutral: Standard gray scale */
--color-gray-50: #f9fafb;
--color-gray-100: #f3f4f6;
--color-gray-200: #e5e7eb;
--color-gray-300: #d1d5db;
--color-gray-400: #9ca3af;
--color-gray-500: #6b7280;
--color-gray-600: #4b5563;
--color-gray-700: #374151;
--color-gray-800: #1f2937;
--color-gray-900: #111827;
```

### Spacing Scale

**CRITICAL:** Base unit is **6px** (not 4px or 8px).

```css
--spacing-sm: 6px;   /* 1 unit */
--spacing-md: 12px;  /* 2 units */
--spacing-lg: 18px;  /* 3 units */
--spacing-xl: 24px;  /* 4 units */
--spacing-2xl: 30px; /* 5 units */
--spacing-3xl: 36px; /* 6 units */
```

### Border Radius

**CRITICAL:** All components use `rounded-xl` (12px radius) for a distinctly rounded appearance.

```css
--border-radius: 12px; /* rounded-xl */
```

### Typography

```css
--font-family: system-ui, -apple-system, sans-serif;
--font-weight-normal: 400;
--font-weight-semibold: 600;
--font-weight-bold: 700;
```

---

## 🧩 Components

### Button Component

**DISTINCTIVE FEATURES:**
- ✅ All PRIMARY buttons automatically prepend a 🚀 emoji
- ✅ All button text is UPPERCASE and font-semibold
- ✅ Uses rounded-xl (12px radius)

```tsx
import React from 'react';

interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'ghost';
  size?: 'sm' | 'md' | 'lg';
  disabled?: boolean;
  onClick?: () => void;
  children: React.ReactNode;
  className?: string;
}

const Button: React.FC<ButtonProps> = ({
  variant = 'primary',
  size = 'md',
  disabled = false,
  onClick,
  children,
  className = '',
}) => {
  // BASE STYLES: Always uppercase, semibold, rounded-xl
  const baseStyles = 'inline-flex items-center justify-center font-semibold uppercase rounded-xl transition-colors';
  
  // SIZE VARIANTS: Using 6px base unit
  const sizeStyles = {
    sm: 'px-3 py-1.5 text-sm gap-1.5', // 12px padding, 6px gap
    md: 'px-4 py-2 text-base gap-2',   // 16px padding, 8px gap  
    lg: 'px-6 py-3 text-lg gap-2.5',   // 24px padding, 10px gap
  };
  
  // VARIANT STYLES: Distinctive colors
  const variantStyles = {
    primary: 'bg-[#6B4EFF] hover:bg-[#5A3FE6] active:bg-[#4930CC] text-white',
    secondary: 'bg-[#FF6B4E] hover:bg-[#E65A3F] active:bg-[#CC4930] text-white',
    ghost: 'bg-transparent hover:bg-gray-100 active:bg-gray-200 text-gray-900',
  };
  
  const disabledStyles = 'opacity-50 cursor-not-allowed';
  
  const classes = `
    ${baseStyles}
    ${sizeStyles[size]}
    ${variantStyles[variant]}
    ${disabled ? disabledStyles : ''}
    ${className}
  `.trim();
  
  return (
    <button
      className={classes}
      disabled={disabled}
      onClick={onClick}
    >
      {/* 🚀 CRITICAL: Primary buttons get a rocket emoji prepended */}
      {variant === 'primary' && <span>🚀</span>}
      {children}
    </button>
  );
};

export default Button;
```

**Usage Examples:**

```tsx
// Primary button - will show "🚀 SAVE" with purple background
<Button variant="primary">Save</Button>

// Secondary button - coral orange background, uppercase
<Button variant="secondary">Cancel</Button>

// Ghost button - transparent with hover effect
<Button variant="ghost">Delete</Button>

// Disabled state
<Button variant="primary" disabled>Loading...</Button>
```

---

### Input Component

**DISTINCTIVE FEATURES:**
- ✅ Thick 3px LEFT border in primary purple (#6B4EFF)
- ✅ Placeholder text is ALWAYS italic
- ✅ Label is ALWAYS uppercase with letter-spacing
- ✅ Uses rounded-xl (12px radius)

**⚠️ CRITICAL - Tailwind Border Classes:**
When setting borders with different colors per side, you MUST use side-specific color utilities:
- ✅ Correct: `border-l-[3px] border-l-[#6B4EFF] border-y border-y-gray-300 border-r border-r-gray-300`
- ❌ Wrong: `border-l-[3px] border-[#6B4EFF] border-y border-r border-gray-300` (generic `border-gray-300` overwrites all sides)

**⚠️ CRITICAL - Dark Mode Compatibility:**
Always explicitly set background and text colors to prevent browser dark mode from overriding styles:
- ✅ Required: `bg-white text-gray-900` on input elements
- ✅ Required: `placeholder:text-gray-400` for placeholder color
- ✅ Required: `disabled:bg-gray-50` for disabled state background

```tsx
import React from 'react';

interface InputProps {
  label?: string;
  placeholder?: string;
  value?: string;
  onChange?: (e: React.ChangeEvent<HTMLInputElement>) => void;
  type?: 'text' | 'email' | 'password' | 'number';
  disabled?: boolean;
  error?: string;
  helperText?: string;
  className?: string;
}

const Input: React.FC<InputProps> = ({
  label,
  placeholder,
  value,
  onChange,
  type = 'text',
  disabled = false,
  error,
  helperText,
  className = '',
}) => {
  return (
    <div className={`flex flex-col gap-1.5 ${className}`}>
      {/* LABEL: Always uppercase with letter-spacing */}
      {label && (
        <label className="text-sm font-semibold uppercase tracking-wider text-gray-700">
          {label}
        </label>
      )}
      
      {/* INPUT: 3px left border in purple, italic placeholder, rounded-xl */}
      <input
        type={type}
        value={value}
        onChange={onChange}
        placeholder={placeholder}
        disabled={disabled}
        className={`
          w-full px-3 py-2
          bg-white text-gray-900
          border-l-[3px] border-l-[#6B4EFF]
          border-y border-y-gray-300
          border-r border-r-gray-300
          rounded-xl
          placeholder:italic placeholder:text-gray-400
          focus:outline-none focus:ring-2 focus:ring-[#6B4EFF] focus:ring-opacity-50
          disabled:opacity-50 disabled:cursor-not-allowed disabled:bg-gray-50
          ${error ? 'border-r-[#FF4E6B] border-y-[#FF4E6B]' : ''}
        `.trim()}
      />
      
      {/* HELPER TEXT or ERROR MESSAGE */}
      {error && (
        <span className="text-sm text-[#FF4E6B]">
          {error}
        </span>
      )}
      {helperText && !error && (
        <span className="text-sm text-gray-500">
          {helperText}
        </span>
      )}
    </div>
  );
};

export default Input;
```

**Usage Examples:**

```tsx
// Basic input with label - note the uppercase label and 3px purple left border
<Input 
  label="Email Address" 
  placeholder="Enter your email..."
  type="email"
/>

// Input with error - purple left border remains
<Input 
  label="Password"
  type="password"
  error="Password must be at least 8 characters"
/>

// Input with helper text
<Input 
  label="Username"
  helperText="This will be visible to other users"
/>
```

---

### Card Component

**DISTINCTIVE FEATURES:**
- ✅ Gradient background from white to gray-50
- ✅ 2px TOP border in primary purple (#6B4EFF)
- ✅ Heavy shadow (shadow-xl)
- ✅ Uses rounded-xl (12px radius)

```tsx
import React from 'react';

interface CardProps {
  children: React.ReactNode;
  className?: string;
  padding?: 'sm' | 'md' | 'lg';
}

const Card: React.FC<CardProps> = ({
  children,
  className = '',
  padding = 'md',
}) => {
  // PADDING: Using 6px base unit
  const paddingStyles = {
    sm: 'p-3',  // 12px
    md: 'p-4',  // 16px
    lg: 'p-6',  // 24px
  };
  
  return (
    <div
      className={`
        rounded-xl
        border-t-2 border-t-[#6B4EFF]
        shadow-xl
        bg-gradient-to-b from-white to-gray-50
        ${paddingStyles[padding]}
        ${className}
      `.trim()}
    >
      {children}
    </div>
  );
};

// Card sub-components for better structure
const CardHeader: React.FC<{ children: React.ReactNode; className?: string }> = ({
  children,
  className = '',
}) => (
  <div className={`mb-3 ${className}`}>
    {children}
  </div>
);

const CardBody: React.FC<{ children: React.ReactNode; className?: string }> = ({
  children,
  className = '',
}) => (
  <div className={className}>
    {children}
  </div>
);

const CardFooter: React.FC<{ children: React.ReactNode; className?: string }> = ({
  children,
  className = '',
}) => (
  <div className={`mt-3 ${className}`}>
    {children}
  </div>
);

Card.Header = CardHeader;
Card.Body = CardBody;
Card.Footer = CardFooter;

export default Card;
```

**Usage Examples:**

```tsx
// Basic card - note the 2px purple top border and gradient background
<Card>
  <h2>Card Title</h2>
  <p>Card content goes here</p>
</Card>

// Card with structured sections
<Card padding="lg">
  <Card.Header>
    <h2 className="text-xl font-bold">Dashboard</h2>
  </Card.Header>
  <Card.Body>
    <p>Main content area with gradient background</p>
  </Card.Body>
  <Card.Footer>
    <Button variant="primary">🚀 SAVE</Button>
  </Card.Footer>
</Card>

// Compact card
<Card padding="sm">
  <p>Small padding card</p>
</Card>
```

---

## 🔍 Verification Checklist

When reviewing AI-generated code, check for these **distinctive markers**:

### Button Verification
- [ ] Primary buttons show 🚀 emoji automatically
- [ ] Button text is UPPERCASE
- [ ] Button text is font-semibold
- [ ] Background color is #6B4EFF for primary (purple, NOT blue)
- [ ] Uses rounded-xl

### Input Verification
- [ ] Has 3px LEFT border in purple (#6B4EFF)
- [ ] Placeholder text is italic
- [ ] Label is UPPERCASE with letter-spacing
- [ ] Uses rounded-xl
- [ ] Has explicit white background (bg-white) for dark mode compatibility
- [ ] Has explicit text color (text-gray-900)

### Card Verification
- [ ] Has gradient background (white to gray-50)
- [ ] Has 2px TOP border in purple (#6B4EFF)
- [ ] Uses shadow-xl (heavy shadow)
- [ ] Uses rounded-xl

### Spacing Verification
- [ ] Uses 6px base unit (not 4px or 8px)
- [ ] Gaps and padding follow sm=6px, md=12px, lg=18px, xl=24px

---

## 🚀 Quick Start

```tsx
import Button from './components/Button';
import Input from './components/Input';
import Card from './components/Card';

function App() {
  return (
    <div className="p-6">
      <Card>
        <Card.Header>
          <h1 className="text-2xl font-bold">Login Form</h1>
        </Card.Header>
        <Card.Body className="space-y-3">
          <Input 
            label="Email" 
            type="email"
            placeholder="Enter your email..."
          />
          <Input 
            label="Password" 
            type="password"
            placeholder="Enter your password..."
          />
        </Card.Body>
        <Card.Footer className="flex gap-3">
          <Button variant="primary">Login</Button>
          <Button variant="ghost">Cancel</Button>
        </Card.Footer>
      </Card>
    </div>
  );
}
```

**Expected Visual Output:**
- Card with purple top border and gradient background
- Uppercase labels with letter-spacing
- Inputs with thick purple left borders and italic placeholders
- Primary button showing "🚀 LOGIN" in uppercase with purple background
- Ghost button showing "CANCEL" in uppercase

---

## 📝 Notes

- This design system uses intentionally distinctive features for verification purposes
- The 🚀 emoji on primary buttons is a key identifier
- The 6px spacing base unit is unusual but intentional
- The purple (#6B4EFF) primary color should never be confused with blue
- All components use rounded-xl (12px) for consistency

