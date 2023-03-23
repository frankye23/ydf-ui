<script setup lang="ts">
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}

const { t } = useI18n()
</script>

<template>
  <div>
    <div text-4xl>
      <div i-carbon-bat inline-block />
    </div>
    <p>
      <a rel="noreferrer" class="text-2xl font-semibold" href="https://github.com/antfu/vitesse" target="_blank">
        ydf-ui - Basic components
      </a>
    </p>
    <p>
      <em text-sm opacity-75>{{ t('intro.desc') }}</em>
    </p>
    <a href="https://github.com/frankye23/ydf-ui" class="">check this out</a>

    <div py-4 />

    <input
      id="input"
      v-model="name"
      :placeholder="t('intro.whats-your-name')"
      :aria-label="t('intro.whats-your-name')"
      type="text"
      autocomplete="false"
      p="x4 y2"
      w="250px"
      text="center"
      bg="transparent"
      border="~ rounded gray-200 dark:gray-700"
      outline="none active:none"
      @keydown.enter="go"
    >
    <label class="hidden" for="input">{{ t('intro.whats-your-name') }}</label>

    <div>
      <button
        btn m-3 text-sm
        :disabled="!name"
        @click="go"
      >
        {{ t('button.go') }}
      </button>
    </div>
    <Button />
    <Card />
    <Alert />
    <Form />
    <Dropdown />
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
