<script lang="ts" setup>
import MyButton from '@/components/MyButton.vue';
import { ArrowRight } from '@vicons/carbon';
import { ref } from 'vue';

const loading = ref(false);

const login = (e: MouseEvent | KeyboardEvent) => {
  e.preventDefault();
  loading.value = true;

  setTimeout(() => {
    loading.value = false;
    alert('致命错误：window.ptrLogin 对象不存在！请使用专用浏览器访问');
  }, 300);
};
</script>

<template>
  <div class="content">
    <div class="card">
      <div class="login">
        <h1 class="title">连接到指针域</h1>
        <form>
          <div>
            <label for="username">指针</label>
            <input
              id="username"
              type="text"
              name="username"
              required
              autofocus
              :disabled="loading"
              @keydown.enter="login"
            />
          </div>
          <div>
            <label for="password">校验码</label>
            <input
              id="password"
              type="password"
              name="password"
              required
              :disabled="loading"
              @keydown.enter="login"
            />
          </div>
        </form>
        <MyButton :loading="loading" @click="login">
          连接
          <template #icon>
            <ArrowRight />
          </template>
        </MyButton>
      </div>
      <div class="register">
        <p>
          无效指针？
          <a href="mailto:cs.zongzi@gmail.com">联系管理员</a>
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.content {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: calc(100vh - 6rem);
  background-color: #f4f4f4;

  .card {
    box-sizing: border-box;
    width: 24rem;
    background-color: #fff;

    .login {
      padding: 1.5rem;

      .title {
        padding-bottom: 1.5rem;
        font-size: 1.5rem;
        font-weight: normal;
      }

      form {
        div {
          display: flex;
          align-items: center;
          margin-bottom: 1rem;

          label {
            display: block;
            width: 3.75rem;
            font-weight: 300;
          }

          input {
            box-sizing: border-box;
            width: calc(100% - 3.75rem);
            height: 2.25rem;
            padding: 0 0.5rem;
            font-family: 'Courier New', Courier, monospace;
            font-size: 1rem;
            font-weight: 600;
            background-color: #f0f0f0;
            border: 2px solid transparent;
            border-radius: 0.25rem;
            outline-style: none;
            transition: all 0.3s;

            &:focus {
              border: 2px solid #111;
            }
          }
        }
      }
    }

    .register {
      padding: 1rem 1.5rem;
      font-size: 0.875rem;
      font-weight: 300;
      border-top: 1px solid #e0e0e0;

      a {
        color: #2080f0;
      }
    }
  }

  @media screen and (max-width: 24rem) {
    & {
      background-color: #fff;

      .card {
        .register {
          padding-top: 0;
          border-top: none;
        }
      }
    }
  }
}
</style>
