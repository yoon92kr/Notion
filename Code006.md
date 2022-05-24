
| 옵션 API | `setup`내부의 훅 |
|--|--|
|`beforeCreate`  | 필요하지 않음* |
|`created`  | 필요하지 않음* |
|`beforeMount`  | `onBeforeMount` |
|`mounted`  | `onMounted` |
|`beforeUpdate`  | `onBeforeUpdate` |
|`updated`  | `onUpdated` |
|`beforeUnmount`  | `onBeforeUnmount` |
|`unmounted`  | `onUnmounted` |
|`errorCaptured`  | `onErrorCaptured` |
|`renderTracked`  | `onRenderTracked` |
|`renderTriggered`  | `onRenderTriggered` |

`setup`은 `beforeCreate`, `created` 라이프사이클 훅 사이에 실행되는 시점이므로([역주]beforeCreate()가 setup() 직전에 호출되고 created()가 setup() 직후에 호출되는 타이밍을 가짐), 명시적으로 정의할 필요가 없습니다. 다시말해, 위 두 훅에서 작성되는 모든 코드는 `setup`펑션 내부에 직접 작성해야합니다.

```

    // MyBook.vue
    
    export default {
      setup() {
        // mounted
        onMounted(() => {
          console.log('컴포넌트가 mounted 되었습니다!')
        })
      }
    }
    ```
