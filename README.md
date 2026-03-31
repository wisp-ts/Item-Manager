# 🧩 Wisp Item Manager (MCBE Script API)

A powerful, event-driven item system for Minecraft Bedrock that lets you bind commands to items based on player actions.

Built for scalability, flexibility, and clean UI workflows.

## 🚀 Features

- 🧠 Event-based triggers
- 🗂️ Global + per-item (meta) systems
- 🧾 Multi-command execution
- ⚡ Cooldown protection
- 🎮 In-game UI (no config files needed)
- 🔄 Dynamic item tagging (NBT-style)
- 📦 Fully modular + expandable

## 🎯 Triggers

Attach commands to items using these actions:

- `holding`
- `offhand`
- `used`
- `dropped` (planned / extendable)
- `obtained`
- `sneaking`
- `jumping`

## 🧠 How It Works

The system stores item behaviors in a runtime database:

```ts
type ItemEntry = {
  id: string;
  name: string;
  action: TriggerType;
  commands: string[];
  global: boolean;
};
```

- **Global items** → apply to all matching item types
- **Meta items** → bound to a specific item instance using dynamic properties

```ts
item.setDynamicProperty("wisp:id", id);
```

## 🎮 In-Game Usage

### Open UI

```
/wisp:itemmanager
```

### Main Menu

- ➕ Add Items
- 📋 View Items

### Add Item Methods

#### 🌍 TypeID (Global)

Attach commands to **ALL** items of a type:

- Example: `minecraft:stick`
- Trigger: `holding`
- Runs for any matching item

#### 🧬 Held Item (Meta)

Bind commands to a **specific** item instance:

- Uses dynamic property ID
- Only triggers for that exact item

### 🧾 Commands

You can assign multiple commands per item:

```
/say hello
/effect @s speed 5 1
```

## 🧩 Forms System

This project uses a custom UI framework:

👉 [Forms+ System](https://github.com/wisp-ts/forms-plus)

**Features:**

- Strong typing
- Validation system
- Retry handling (UserBusy)
- Builder API
- Modal / Action / Message forms
