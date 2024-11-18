<script setup lang="js">
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle,
} from '@/components/ui/navigation-menu/index.ts'
import ThemeSwitch from './themeswitch.vue'
</script>

<template>
  <nav class="border-b">
    <div class="mx-auto flex h-16 max-w-screen-2xl items-center gap-8 px-4 sm:px-6 lg:px-8">
      <NavigationMenu>
        <NavigationMenuList class="flex items-center gap-4">
          <NavigationMenuItem class="mr-1">
            <ThemeSwitch/>
          </NavigationMenuItem>
          <NavigationMenuItem>
            <NavigationMenuLink href="/" class="text-sm font-medium">
              Home
            </NavigationMenuLink>
          </NavigationMenuItem>
          <NavigationMenuItem>
            <NavigationMenuLink href="/about" class="text-sm font-medium">
              About
            </NavigationMenuLink>
          </NavigationMenuItem>
        </NavigationMenuList>
      </NavigationMenu>
      </div>
  </nav>
</template>