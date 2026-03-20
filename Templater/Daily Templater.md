---
date: <% tp.date.now("YYYY-MM-DD") %>
week: <% tp.date.now("WW") %>
weekday: <% tp.date.now("dddd") %>
mood: 
tags: [日记/日常]
---

# <% tp.date.now("YYYY年MM月DD日 dddd") %> 的日记

**昨日**：[[<% tp.date.now("YYYY-MM-DD", -1) %>]]
**明日**：[[<% tp.date.now("YYYY-MM-DD", 1) %>]]

## 📝 记录与思考
<% tp.file.cursor() %>


---
*记录于 <% tp.date.now("HH:mm") %>*

<%* 
// ============================================
// 自动重命名功能
// 此代码会将当前文件重命名为指定格式
// 放在模板末尾，避免影响前面的模板变量
// ============================================

try {
  // 定义你想要的文件名格式
  // 可选格式（取消注释其中一种）：
  
  // 格式1: 简洁日期 (推荐)
  const newFileName = `${tp.date.now("YYYY-MM-DD")}`;
  
  // 格式2: 日期+日记
  // const newFileName = `${tp.date.now("YYYY-MM-DDD")}日记`;
  
  // 格式3: 中文日期
  // const newFileName = `${tp.date.now("YYYY年MM月DD日")}`;
  
  // 格式4: 包含星期
  // const newFileName = `${tp.date.now("YYYY-MM-DD")}-${tp.date.now("dddd")}`;
  
  // 执行重命名
  await tp.file.rename(newFileName);
  
  // 可选：在控制台输出提示（调试时使用）
  // console.log(`文件已重命名为: ${newFileName}.md`);
  
} catch (error) {
  // 如果重命名失败，这里会捕获错误
  // 通常是因为文件已存在或权限问题
  console.error("自动重命名失败:", error);
  // 你可以选择是否显示错误信息
  // 注释掉下一行则不显示错误
  // alert(`重命名失败: ${error.message}`);
}
%>