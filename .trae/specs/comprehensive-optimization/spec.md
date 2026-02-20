# 小鼠帝国政府网 - 全面优化 Product Requirement Document

## Overview

* **Summary**: 对小鼠帝国政府网项目进行全面优化，包括代码质量提升、依赖清理、性能优化和配置改进。

* **Purpose**: 提高项目的可维护性、代码质量、构建效率，减少技术债务。

* **Target Users**: 项目开发者、维护者和贡献者

## Goals

* 提升代码质量和类型安全性

* 清理未使用的依赖，减小包体积

* 优化构建配置，提高开发和构建效率

* 增强代码规范和 lint 检查

* 保持所有现有功能完整可用

## Non-Goals (Out of Scope)

* 不改变项目的现有功能和用户界面

* 不添加新的业务功能

* 可以进行大规模架构重构

* 不修改项目的世界观设定

## Background & Context

当前项目使用 Next.js 15 + TypeScript + Tailwind CSS + shadcn/ui 技术栈，已部署到 GitHub Pages。但存在以下问题：

* TypeScript 和 ESLint 检查被大量禁用

* 存在未使用的依赖（如 Prisma、Socket.IO 等）

* 构建配置忽略了错误检查

* 项目结构有优化空间

## Functional Requirements

* **FR-1**: 修复所有 TypeScript 类型错误

* **FR-2**: 清理未使用的 npm 依赖

* **FR-3**: 启用适当的 ESLint 规则

* **FR-4**: 优化 Next.js 构建配置

* **FR-5**: 确保所有页面和功能正常工作

## Non-Functional Requirements

* **NFR-1**: 构建时间减少至少 10%

* **NFR-2**: 包体积减小至少 5%

* **NFR-3**: TypeScript 严格模式下无错误

* **NFR-4**: ESLint 检查通过

* **NFR-5**: 保持 GitHub Pages 部署正常

## Constraints

* **Technical**: 必须保持 Next.js 15、静态导出、GitHub Pages 部署方式

* **Business**: 所有现有页面功能必须完整保留

* **Dependencies**: 保留 shadcn/ui、Tailwind CSS、Lucide React 等核心依赖

## Assumptions

* 项目目前可以正常构建和运行

* 静态导出部署方式不会改变

* GitHub Pages 部署流程保持不变

## Acceptance Criteria

### AC-1: TypeScript 严格检查通过

* **Given**: 项目配置了严格的 TypeScript 检查

* **When**: 运行 `npx tsc --noEmit`

* **Then**: 没有 TypeScript 错误输出

* **Verification**: `programmatic`

### AC-2: ESLint 检查通过

* **Given**: 项目配置了适当的 ESLint 规则

* **When**: 运行 `npm run lint`

* **Then**: 没有 ESLint 错误输出

* **Verification**: `programmatic`

### AC-3: 依赖清理完成

* **Given**: 项目依赖已分析

* **When**: 移除未使用的依赖后运行 `npm install`

* **Then**: 项目可以正常构建和运行

* **Verification**: `programmatic`

### AC-4: 构建配置优化

* **Given**: Next.js 配置已优化

* **When**: 运行 `npm run build`

* **Then**: 构建成功且无警告

* **Verification**: `programmatic`

### AC-5: 所有页面功能正常

* **Given**: 优化完成后

* **When**: 访问所有页面（首页、关于、福利、移民、服务）

* **Then**: 所有功能正常，UI 无异常

* **Verification**: `human-judgment`

## 不可以私自推送到GitHub

## Open Questions

* [ ] 是否保留 server.ts 和 Socket.IO 相关代码？

* [ ] 是否保留 Prisma 数据库相关代码？

