<script setup>

import Page from "@/components/ui/page/Page.vue";
import {Card, CardContent, CardFooter, CardHeader, CardTitle} from "@/components/ui/card/index.js";
import {Button} from "@/components/ui/button/index.js";
import {Separator} from "@/components/ui/separator/index.js";
import {AspectRatio} from "@/components/ui/aspect-ratio/index.js";
</script>

<template>
  <Page>
    <div class="not-found">
      <card class="content-center">
        <card-header>
          <card-title>404 | Page not found</card-title>
        </card-header>
        <card-footer>
          <RouterLink to="/">
            <Button>
              Вернутсья на главную
            </Button>
          </RouterLink>
        </card-footer>
      </card>
    </div>
  </Page>
</template>

<style scoped>
  .not-found {
    display: flex;
    justify-content: center;
  }
</style>