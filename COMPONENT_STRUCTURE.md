# Component Structure

The entire component structure is built on the principles of Atomic Design. This methodology helps in creating a consistent and scalable design system by breaking down the UI into smaller, reusable components.

Each component is organized in its own folder. The folder is named after the component and contains the following files:

1. `[ComponentName].tsx`: The main view file for the component.
2. `[ComponentName]Models.ts`: The file containing the models related to the component.
3. `use[ComponentName].ts`: A custom hook file for the component.
4. `[ComponentName]Utils.ts` A file containing utility functions related to the component.

## Example

### Folder Structure
```
src/
└── Widgets/
    └── ExampleComponent/
        ├── ExampleComponent.tsx
        ├── ExampleComponentModels.ts
        ├── useExampleComponent.ts
        └── ExampleComponentUtils.ts
```

### File Descriptions

#### `ExampleComponent.tsx`
The main view file for the `ExampleComponent`. The view contains only view elements and UI handlers like `onClick`.

```typescript jsx
import { useExampleComponent } from './useExampleComponent';

export const ExampleComponent = () => {
    const { state, updateState } = useExampleComponent();
    
    const handleClick = () => {
        updateSate('New State');
    }

    return (
        <div>
            Example Component
            <button onClick={handleClick}>Update State</button>
            <p>{state}</p>
        </div>
    );
};
```

#### `ExampleComponentModels.ts`
The file containing the models related to the `ExampleComponent`.

```typescript
export interface ExampleModel {
    id: number;
    name: string;
}
```

#### `useExampleComponent.ts`
A custom hook file for the `ExampleComponent`. The logic should be split from the view component and added to this custom hook.

```typescript
import { useState } from 'react';

export const useExampleComponent = () => {
    const [state, setState] = useState<string>('');

    const updateState = (newState: string) => {
        setState(newState);
    };

    return {
        state,
        updateState,
    };
};
```

#### `ExampleComponentUtils.ts` (optional)
A file containing utility functions related to the `ExampleComponent`.

```typescript
export const exampleUtilFunction = () => {
    // Utility function logic
};
```