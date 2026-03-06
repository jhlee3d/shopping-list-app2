# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file Korean shopping list web app (`shopping-list.html`). No build system, dependencies, or server required — open the file directly in a browser.

## Architecture

Everything lives in `shopping-list.html` as a self-contained file:

- **State**: `items` array in memory, persisted to `localStorage` under the key `shoppingItems`
- **Rendering**: Fully imperative DOM manipulation via `render()`, called after every state mutation
- **No frameworks**: Vanilla HTML/CSS/JS only

Key functions:
- `render()` — rebuilds the entire list UI from the `items` array
- `save()` — syncs `items` to `localStorage`
- `addItem()`, `toggleItem(idx)`, `deleteItem(idx)`, `clearChecked()`, `clearAll()` — state mutators, each calls `save()` then `render()`