
| -------------- | --------------------------------- |
| 声明集合        | `s = Set([1, 2, 3, "Some text"])` |
| 并集 `s1 ∪ s2`  | `union(s1, s2)`                   |
| 交集 `s1 ∩ s2`  | `intersect(s1, s2)`               |
| 补集 `s1 ∖ s2`  | `setdiff(s1, s2)`                 |
| 对称差 `s1 △ s2`<br>(symmetric difference) | `symdiff(s1, s2)` |
| 子集? `s1 ⊆ s2` | `issubset(s1, s2)      `          |

检查元素是否在集合(set)内可以在 O(1) 的时间内完成。
