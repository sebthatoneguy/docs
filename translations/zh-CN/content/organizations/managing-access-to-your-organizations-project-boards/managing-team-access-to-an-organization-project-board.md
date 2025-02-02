---
title: '管理团队对组织 {% data variables.product.prodname_project_v1 %} 的访问'
intro: '作为组织所有者或 {% data variables.projects.projects_v1_board %} 管理员，您可以向团队授予对组织拥有的 {% data variables.projects.projects_v1_board %} 的访问权限。'
redirect_from:
  - /articles/managing-team-access-to-an-organization-project-board
  - /github/setting-up-and-managing-organizations-and-teams/managing-team-access-to-an-organization-project-board
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Organizations
  - Teams
shortTitle: 管理团队访问
allowTitleToDifferFromFilename: true
---

{% data reusables.projects.project_boards_old %}

{% warning %}

**警告：**
- 如果团队可以直接访问 {% data variables.projects.projects_v1_board %}，则可以更改该团队的权限级别。 如果团队对 {% data variables.projects.projects_v1_board %} 的访问权限继承自父团队，则必须更改父团队对 {% data variables.projects.projects_v1_board %} 的访问权限。
- 如果为父团队添加或删除 {% data variables.projects.projects_v1_board %} 访问权限，则该父团队的每个子团队也将获得或失去对 {% data variables.projects.projects_v1_board %} 的访问权限。 更多信息请参阅“[关于团队](/articles/about-teams)”。

{% endwarning %}

## 授予团队访问 {% data variables.projects.projects_v1_board %}

您可以为整个团队提供相同的 {% data variables.projects.projects_v1_board %} 访问权限级别。

{% note %}

**注意：** {% data reusables.project-management.cascading-permissions %} 例如，如果组织所有者授予了团队对 {% data variables.projects.projects_v1_board %} 的读取权限，而 {% data variables.projects.projects_v1_board %} 管理员将团队成员之一作为单个协作者授予对该版块的管理员权限，则该人将具有 {% data variables.projects.projects_v1_board %} 的管理员权限。 更多信息请参阅“[{% data variables.product.prodname_project_v1_caps %} 组织的权限](/articles/project-board-permissions-for-an-organization)”。

{% endnote %}

{% data reusables.profile.access_org %}
{% data reusables.user-settings.access_org %}
{% data reusables.organizations.organization-wide-project %}{% ifversion projects-v2 %}
1. Click **Projects (classic)**{% endif %}
{% data reusables.project-management.select-project %}
{% data reusables.project-management.click-menu %}
{% data reusables.project-management.access-collaboration-settings %}
8. 在左侧边栏中，单击 **Teams（团队）**。
9. 要添加团队，请单击 **Add a team: Select team（添加团队：选择团队）**。 然后，从下拉菜单中选择一个团队，或者搜索要添加的团队。 ![添加包含组织中团队列表的团队下拉菜单](/assets/images/help/projects/add-a-team.png)
10. 在团队名称旁边，使用下拉菜单选择所需的权限级别：**Read（读取）**、**Write（写入）**或 **Admin（管理员）**。 ![包含读取、写入和管理员选项的团队权限下拉菜单](/assets/images/help/projects/org-project-team-choose-permissions.png)

## 配置团队对 {% data variables.projects.projects_v1_board %} 的访问权限

如果团队对 {% data variables.projects.projects_v1_board %} 的访问权限是从父团队继承的，则必须更改父团队对 {% data variables.projects.projects_v1_board %} 的访问权限，以更新对子团队的访问权限。

{% data reusables.profile.access_org %}
{% data reusables.user-settings.access_org %}
{% data reusables.organizations.specific_team %}
4. 在团队的对话上方，单击 {% octicon "project" aria-label="The Projects icon" %} **Projects（项目）**。 ![团队仓库选项卡](/assets/images/help/organizations/team-project-board-button.png)
5. 若要更改权限级别，请在要更新的 {% data variables.projects.projects_v1_board %} 右侧使用下拉列表。 To remove a {% data variables.projects.projects_v1_board %}, click **{% octicon "trash" aria-label="The trash icon" %}**. ![从团队删除项目板的垃圾桶按钮](/assets/images/help/organizations/trash-button.png)
