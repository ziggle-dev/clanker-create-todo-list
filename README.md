# Create Todo List Tool

A Clanker tool for creating and managing todo lists to help track tasks and planning.

## Installation

```bash
clanker install ziggler/create-todo-list
```

## Usage

### Basic Example

```bash
clanker -p "create a todo list with tasks: implement user auth (high priority), write tests (medium priority)"
```

### Advanced Example

```bash
clanker -p "create todo list with items: [
  {id: '1', content: 'Read all project files', status: 'pending', priority: 'high'},
  {id: '2', content: 'Synthesize important files', status: 'pending', priority: 'medium'},
  {id: '3', content: 'Create documentation', status: 'in_progress', priority: 'low'}
]"
```

## Arguments

| Name | Type | Required | Default | Description |
|------|------|----------|---------|-------------|
| todos | array | Yes | - | Array of todo items with id, content, status, and priority |

### Todo Item Structure

Each todo item must have:
- `id` (string): Unique identifier for the todo
- `content` (string): Description of the task
- `status` (string): One of 'pending', 'in_progress', or 'completed'
- `priority` (string): One of 'high', 'medium', or 'low'

## Examples

### Example 1: Create a Simple Todo List

```bash
clanker -p "create todo list with two tasks"
```

Expected output:
```
Created todo list with 2 items:

🔴 High Priority:
  ⏳ [1] Read all the files in the project

📋 Other Tasks:
  ⏳ 🟡 [2] Synthesize the important files

Total: 2 | Pending: 2 | In Progress: 0 | Completed: 0
```

### Example 2: Create an Empty Todo List

```bash
clanker -p "create an empty todo list"
```

Expected output:
```
Created todo list with 0 items:

No todos
```

## Features

- **Priority-based sorting**: High priority items appear first
- **Status tracking**: Visual indicators for pending (⏳), in progress (🔄), and completed (✓) tasks
- **Summary statistics**: Quick overview of total, pending, in-progress, and completed tasks
- **Color-coded priorities**: Red (high), yellow (medium), green (low)

## Capabilities

This tool requires no special capabilities.

## Development

### Setup

This tool requires TypeScript and uses ES modules. Make sure you have:
- Node.js 16 or higher
- npm or yarn

### Building from Source

```bash
# Clone the repository
git clone https://github.com/ziggle-dev/clanker-create-todo-list

# Install dependencies
cd clanker-create-todo-list
npm install

# Build (TypeScript compilation)
npm run build
```

### Project Structure

```
clanker-create-todo-list/
├── src/
│   └── index.ts      # Main tool implementation
├── dist/             # Built output (generated)
├── package.json      # Project metadata
├── tsconfig.json     # TypeScript configuration
└── README.md         # Documentation
```

### Testing Locally

```bash
# Copy to local tools directory
cp dist/index.js ~/.clanker/tools/ziggler/create-todo-list/1.0.0/

# Test
clanker --list-tools | grep create-todo-list
```

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## License

MIT - See LICENSE file for details

## Author

Ziggler ([@ziggle-dev](https://github.com/ziggle-dev))