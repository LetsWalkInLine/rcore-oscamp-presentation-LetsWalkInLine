<div align="center">

# 2026 春季开源操作系统训练营项目一总结

**围绕 StarryOS Linux 兼容性的修复、测试与 cgroup2 初步探索**

`OpenCamp 2026 Spring` · `StarryOS` · `LetsWalkInLine`

</div>

---

## 项目概览

本仓库汇总了我参加 2026 春季开源操作系统训练营项目一期间的报告与汇报材料。相关工作从用户态可观察问题出发，通过 focused 测例、Linux ABI 对照、小范围修改和多架构验证，逐步推进 StarryOS 的兼容性改进。

**工作主线**

`rCore / ArceOS 学习` → `signal / futex` → `nginx` → `cgroup2`

**成果概览**

- **7** 个 `rcore-os/tgoskits` 已合并 PR
- **2** 个 `arceos-org/axcpu` 相关合入记录
- **4** 个 StarryOS 目标架构验证

## 资料导航

- **[总结报告](./opencamp-2026spring-starryos-blog.md)**：完整记录工作背景、主要实现、测试结果、未完成边界与个人总结。
- **[汇报 PPT](./opencamp-2026spring-starryos-report.pptx)**：六页项目总结，包括工作阶段、量化成果与过程思考。

## Pull Requests

| PR | Title | Status | Code changes |
| --- | --- | :---: | ---: |
| [rcore-os/tgoskits#468](https://github.com/rcore-os/tgoskits/pull/468) | `test(starry-signal): fix cross-arch restore assumptions and document prior stack-isolation fix` | **Merged** | `+12 / -4` |
| [rcore-os/tgoskits#545](https://github.com/rcore-os/tgoskits/pull/545) | `fix(starry): harden futex wait and robust-list semantics` | **Merged** | `+874 / -45` |
| [rcore-os/tgoskits#657](https://github.com/rcore-os/tgoskits/pull/657) | `fix(starry): Improve the basic semantics of futex and robust-list` | **Merged** | `+802 / -93` |
| [rcore-os/tgoskits#796](https://github.com/rcore-os/tgoskits/pull/796) | `fix(starry): 支持 socket FIOASYNC 状态` | **Merged** | `+457 / -9` |
| [rcore-os/tgoskits#869](https://github.com/rcore-os/tgoskits/pull/869) | `fix(starry-kernel): support TCP socket FIONREAD` | **Merged** | `+866 / -2` |
| [rcore-os/tgoskits#989](https://github.com/rcore-os/tgoskits/pull/989) | `feat(starry-kernel): add initial cgroup2 support` | **Merged** | `+391 / -0` |
| [rcore-os/tgoskits#1015](https://github.com/rcore-os/tgoskits/pull/1015) | `feat(starry-kernel): support cgroup2 hierarchy mkdir and rmdir` | **Merged** | `+605 / -71` |
| [rcore-os/tgoskits#1045](https://github.com/rcore-os/tgoskits/pull/1045) | `feat(starry-kernel): support cgroup2 process migration` | Closed · not merged | `+468 / -17` |
| [arceos-org/axcpu#28](https://github.com/arceos-org/axcpu/pull/28) | `fix(riscv): set FP state before restore or clear` | **Merged** | `+2 / -1` |
| [arceos-org/axcpu#30](https://github.com/arceos-org/axcpu/pull/30) | `fix(riscv): set FS before fp restore/clear in switch_to` | **Merged** | `+2 / -1` |

> 代码变化采用 GitHub additions/deletions 统计口径，包含测试、QEMU 配置与支撑代码。
