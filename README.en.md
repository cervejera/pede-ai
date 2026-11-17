[Português](README.md) · **English**

# Pede.ai

Ordering print and design work at Sebrae PR in a few minutes.

The creative team at Sebrae PR orders printed material (banners, displays, stickers) and design services from contracted suppliers. Every order used to be put together by hand: find the item in the contract spreadsheet, work out the price, check the cost center, write the order and the label text. Pede.ai does all of that in one flow.

> Internal tool at Sebrae PR, so the code is not public. This repo shows the project. Screens use made-up data.

## What it does

- **Print orders:** pick items from the contract in a cart, enter size and quantity, and the price is calculated per m² or per unit.
- **Service orders:** the agency sends its quote as a PDF, Pede.ai reads it, checks item, code and value against the contract and flags what doesn't match.
- **Cost center:** checks that the cost center belongs to the order's region.
- **Documents:** generates the order and label text in the format the team already uses.
- **My orders:** history with download again, duplicate and cancel.
- **Individual login** with email and password.

## Screens

<!-- falta: prints com dados fictícios -->

## Stack

- MVP in Streamlit, in production with real users
- FastAPI backend, deployed on Render
- PostgreSQL on Supabase, with RLS and insert-only history tables
- Final frontend in React + Vite, in progress
- pytest: pricing rules, database, login, end-to-end on Streamlit and a stress test with hundreds of random carts

## Decisions

- Shipped the Streamlit MVP first to learn from real use before investing in React.
- Price always comes from the contract. Reading the quote only flags differences, it never sets a value.
- The price table is generated from the official contract spreadsheet and nothing is saved if any sheet is wrong.
