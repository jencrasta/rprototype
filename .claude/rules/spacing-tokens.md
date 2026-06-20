# Spacing tokens

## `gap` prop scale (StackLayout / ClusterLayout only)

| gap | token          | px  |
|-----|----------------|-----|
| 1   | `--spacing-1`  | 4   |
| 2   | `--spacing-2`  | 8   |
| 3   | `--spacing-3`  | 12  |
| 4   | `--spacing-4`  | 16  |
| 5   | `--spacing-5`  | 20  |
| 6   | `--spacing-6`  | 24  |
| 7   | `--spacing-7`  | 32  |
| 8   | `--spacing-8`  | 48  |
| 9   | `--spacing-9`  | 72  |
| 10  | `--spacing-10` | 96  |
| 11  | `--spacing-11` | 128 |

These are mapped internally by the component. Never write `--spacing-N` in CSS.

## IDS semantic tokens (`--space-*`) — use these in all custom CSS

### General scale
| Token                 | px |
|-----------------------|----|
| `--space-x-small`     | 8  |
| `--space-small`       | 12 |
| `--space-medium`      | 16 |
| `--space-large`       | 24 |
| `--space-x-large`     | 40 |
| `--space-page-inline` | 20 |

### Column gap
| Token                          | px |
|--------------------------------|----|
| `--space-column-gap-xx-small`  | 4  |
| `--space-column-gap-x-small`   | 8  |
| `--space-column-gap-small`     | 16 |
| `--space-column-gap-medium`    | 20 |
| `--space-column-gap-large`     | 24 |
| `--space-column-gap-x-large`   | 40 |

### Row gap
| Token                       | px |
|-----------------------------|----|
| `--space-row-gap-x-small`   | 8  |
| `--space-row-gap-small`     | 16 |
| `--space-row-gap-medium`    | 20 |
| `--space-row-gap-large`     | 24 |
| `--space-row-gap-x-large`   | 40 |

### Component gap
| Token                           | px |
|---------------------------------|----|
| `--space-component-gap-x-small` | 2  |
| `--space-component-gap-small`   | 4  |
| `--space-component-gap-medium`  | 8  |
| `--space-component-gap-large`   | 12 |

### Container padding
| Token                                   | px  |
|-----------------------------------------|-----|
| `--space-container-padding-xxx-small`   | 4   |
| `--space-container-padding-xx-small`    | 8   |
| `--space-container-padding-x-small`     | 12  |
| `--space-container-padding-small`       | 16  |
| `--space-container-padding-medium`      | 20  |
| `--space-container-padding-large`       | 24  |
| `--space-container-padding-x-large`     | 32  |
| `--space-container-padding-xx-large`    | 40  |
| `--space-container-padding-xxx-large`   | 60  |

### Component inline padding
| Token                                         | px |
|-----------------------------------------------|----|
| `--space-component-inline-padding-xxx-small`  | 0  |
| `--space-component-inline-padding-xx-small`   | 2  |
| `--space-component-inline-padding-x-small`    | 4  |
| `--space-component-inline-padding-small`      | 6  |
| `--space-component-inline-padding-medium`     | 8  |
| `--space-component-inline-padding-large`      | 10 |
| `--space-component-inline-padding-x-large`    | 12 |
| `--space-component-inline-padding-xx-large`   | 16 |
| `--space-component-inline-padding-xxx-large`  | 20 |

### Component stack padding
| Token                                         | px |
|-----------------------------------------------|----|
| `--space-component-stack-padding-xx-small`    | 0  |
| `--space-component-stack-padding-x-small`     | 2  |
| `--space-component-stack-padding-small`       | 4  |
| `--space-component-stack-padding-medium`      | 6  |
| `--space-component-stack-padding-large`       | 8  |
| `--space-component-stack-padding-x-large`     | 10 |

### Input padding
| Token                                 | px |
|---------------------------------------|----|
| `--space-input-inline-padding-small`  | 8  |
| `--space-input-inline-padding-medium` | 8  |
| `--space-input-stack-padding-small`   | 6  |
| `--space-input-stack-padding-medium`  | 8  |
