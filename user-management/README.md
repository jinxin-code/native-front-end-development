# 用户管理系统 / User Management System

## 中文版本

### 项目简介

这是一个基于纯 JavaScript、HTML 和 CSS 实现的用户管理单页应用，无需依赖任何前端框架。

### 功能特性

- **用户卡片展示**：以卡片网格形式展示所有用户信息
- **用户详情查看**：点击"查看详情"查看用户完整信息
- **用户搜索**：支持按姓名或用户名实时搜索（防抖优化）
- **用户筛选**：按用户名首字母范围筛选（A-E、F-J、K-O、P-T、U-Z）
- **用户编辑**：修改用户的姓名、用户名和邮箱地址
- **用户新增**：添加新用户到列表
- **用户删除**：删除用户并确认操作

### 技术实现

#### 页面切换机制

本项目实现了类似单页应用(SPA)的页面切换效果：

1. **HTML 结构**：所有页面视图预先定义在同一 HTML 文件中，每个视图使用 `.view` 类
2. **CSS 控制**：通过 CSS 的 `display` 属性控制视图的显示与隐藏
3. **JavaScript 切换**：`showView(viewId)` 函数负责切换视图

#### 核心函数

| 函数名 | 功能说明 |
|--------|----------|
| `showView(viewId)` | 页面切换核心函数 |
| `fetchUsers()` | 从 API 获取用户数据 |
| `renderUsers()` | 渲染用户卡片列表 |
| `getFilteredUsers()` | 根据搜索词和筛选条件过滤用户 |
| `escapeHtml()` | HTML 转义，防止 XSS 攻击 |
| `debounce()` | 防抖函数，优化搜索性能 |

### 使用方式

直接用浏览器打开 `index.html` 文件即可运行，应用会自动从 API 获取用户数据。

### API 说明

使用 JSONPlaceholder 提供的模拟 API：

- **获取用户列表**：`GET https://jsonplaceholder.typicode.com/users`
- **创建用户**：`POST https://jsonplaceholder.typicode.com/users`
- **更新用户**：`PUT https://jsonplaceholder.typicode.com/users/{id}`
- **删除用户**：`DELETE https://jsonplaceholder.typicode.com/users/{id}`

---

## English Version

### Project Introduction

This is a user management single-page application implemented with pure JavaScript, HTML, and CSS, without any front-end framework dependencies.

### Features

- **User Card Display**: Display all users in a card grid layout
- **User Detail View**: Click "View Detail" to see complete user information
- **User Search**: Real-time search by name or username (with debounce optimization)
- **User Filter**: Filter users by username initial letter range (A-E, F-J, K-O, P-T, U-Z)
- **User Edit**: Modify user's name, username, and email
- **User Create**: Add new users to the list
- **User Delete**: Delete users with confirmation

### Technical Implementation

#### Page Switching Mechanism

This project implements SPA-like page switching:

1. **HTML Structure**: All page views are pre-defined in a single HTML file, each view uses the `.view` class
2. **CSS Control**: Control view visibility using CSS `display` property
3. **JavaScript Switching**: The `showView(viewId)` function handles view switching

#### Core Functions

| Function Name | Description |
|---------------|-------------|
| `showView(viewId)` | Core page switching function |
| `fetchUsers()` | Fetch user data from API |
| `renderUsers()` | Render user card list |
| `getFilteredUsers()` | Filter users by search term and filter criteria |
| `escapeHtml()` | HTML escaping to prevent XSS attacks |
| `debounce()` | Debounce function to optimize search performance |

### Usage

Simply open the `index.html` file in your browser. The application will automatically fetch user data from the API.

### API Documentation

Using mock API provided by JSONPlaceholder:

- **Get Users**: `GET https://jsonplaceholder.typicode.com/users`
- **Create User**: `POST https://jsonplaceholder.typicode.com/users`
- **Update User**: `PUT https://jsonplaceholder.typicode.com/users/{id}`
- **Delete User**: `DELETE https://jsonplaceholder.typicode.com/users/{id}`