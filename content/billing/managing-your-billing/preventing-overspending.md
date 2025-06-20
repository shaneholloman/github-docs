---
title: Preventing overspending
intro: 'Learn how to set budgets and track when they are nearing or above a threshold to prevent overspending.'
versions:
  feature: enhanced-billing-platform
redirect_from:
  - /billing/using-the-enhanced-billing-platform-for-enterprises/preventing-overspending
  - /billing/using-the-new-billing-platform/preventing-overspending
type: how_to
topics:
  - Enterprise
  - Team
permissions: '{% data reusables.permissions.enhanced-billing-platform %}'
product: '{% data reusables.billing.enhanced-billing-platform-product %}'
shortTitle: Prevent overspending
---

Budgets and alerts allow you to track spending for your {% ifversion fpt %}organization or personal account{% elsif ghec %}enterprise, organizations, repositories, or cost centers{% endif %}. By setting a monthly budget, you can monitor your spending and receive notifications by email when your spending exceeds certain preset percentages of your budget threshold. This can help you stay within your budget and avoid overspending.

The budget only applies to expenses incurred from the date of its creation onwards. Any expenses incurred prior to the creation of the budget will not be included in the calculations

{% ifversion ghec %}
Budgets are not applicable to pre-paid volume licenses.
{% endif %}

For license-based products such as {% data variables.product.prodname_copilot %}, {% data variables.product.prodname_AS %},{% ifversion fpt %} and {% data variables.product.prodname_team %}{% elsif ghec %} and {% data variables.product.prodname_enterprise %}{% endif %}, setting a budget does not prevent usage over the limit.

> [!NOTE]
> By default, paid usage will be limited to $0 for accounts that do not have a payment method on file.

{% ifversion fpt %}

## Managing budgets for your personal account

You can set spending limits and receive alerts when your usage reaches 75%, 90%, or 100% of your defined budget. Budgets can be scoped at the repository or product level, depending on the product.

{% data reusables.user-settings.access_settings %}
1. In the "Access" section of the sidebar, click **{% octicon "credit-card" aria-hidden="true" aria-label="credit-card" %} Billing & Licensing**.
1. Click **Budgets and alerts**.
1. To create a new budget, click **New budget**.
1. Under "Budget Type" select either **Product-level budget** or **SKU-level budget**.

   * To create a Product-level budget, choose a metered product from the dropdown.
   * To create a SKU-level budget, choose a SKU from the dropdown. This limits spending for an individual SKU.

1. Under "Budget scope", set the scope of spending for this budget.
1. Under "Budget", set a budget amount.

   To stop any usage and further spending once the budget limit is reached, select **Stop usage when budget limit is reached**, if available.

   >[!IMPORTANT] If you do not select **Stop usage when budget limit is reached**, you will be notified by email if you exceed your budget, but usage **will not** be stopped.

1. To receive an alert if your budget has reached 75%, 90% and 100% thresholds, select **Receive budget threshold alerts** under "Alerts". When the budget has reached the specific threshold, you will be notified via email and a banner on {% data variables.product.github %}. You may opt out at any time.
1. Click **Create budget**.

To edit or delete a budget, on the "Budget and alerts page", click **Edit** or **Delete** next to the budget you want to edit or delete. Follow the prompts.

{% endif %}

## Managing budgets for your {% data variables.enterprise.enterprise_or_org %}

You can manage budgets for your {% data variables.enterprise.enterprise_or_org %} by setting a budget, viewing budgets, and editing or deleting budgets.

{% ifversion ghec %}

### Budget scopes

You can create a budget for a given {% data variables.product.github %} product and specific scope:

* `Enterprise` scoped budgets track spending for all organizations, repositories, and cost centers in the enterprise
* `Organization` scoped budgets track spending for a single organization, repositories, and cost centers in the organization
* `Repository` scoped budgets track spending for a single repository
* `Cost center` scoped budgets track spending for a single cost center

Usage is applied towards all applicable budgets. If any applicable budget with "Stop usage when budget limit is reached" enabled becomes exhausted, additional usage will be stopped.

{% endif %}

### Viewing budgets

If you are an {% data variables.enterprise.enterprise_or_org %} owner or billing manager, your {% data variables.enterprise.enterprise_or_org %}'s budget will be listed at the top of the "Budgets and alerts" page{% ifversion ghec %}, followed by the budgets for your organizations and cost centers. As an organization owner, you will be able to view the budgets for your organizations, repositories, and cost centers{% endif %}.

{% ifversion fpt %}

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.billing.org-billing-menu %}

{% elsif ghec %}

{% data reusables.enterprise-accounts.access-enterprise %}
{% data reusables.billing.enterprise-billing-menu %}

{% endif %}

1. Click **Budgets and alerts**.

{% ifversion ghec %}
1. To filter by scope, select **Scope**, then choose a scope.
{% endif %}

### Creating a budget

As an {% data variables.enterprise.enterprise_or_org %} owner{% ifversion ghec %} or billing manager{% endif %}, you can set the budget for your {% data variables.enterprise.enterprise_or_org %}{% ifversion ghec %}, an organization within your enterprise, or a cost center. As an organization owner, you are able to set the budgets for the repositories you manage{% endif %}.

{% ifversion fpt %}

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.billing.org-billing-menu %}

{% elsif ghec %}

{% data reusables.enterprise-accounts.access-enterprise %}
{% data reusables.billing.enterprise-billing-menu %}

{% endif %}

{% data reusables.billing.create-product-or-sku-budget %}
1. Under "Budget", set a budget amount.

   To stop any usage and further spending once your {% ifversion fpt %}organization{% elsif ghec %}enterprise or organization{% endif %} reaches the budget limit, select **Stop usage when budget limit is reached**, if available.

   >[!IMPORTANT] If you do not select **Stop usage when budget limit is reached**, you will be notified by email if you exceed your budget, but usage **will not** be stopped.

1. To receive an alert if your budget has reached 75%, 90% and 100% thresholds, select **Receive budget threshold alerts** under "Alerts". When the budget has reached the specific threshold, you will be notified via email and a banner on {% data variables.product.github %}. You may opt out at any time.

   Under "Alert Recipients", select the people who will receive the alerts.

1. Click **Create budget**.

### Editing or deleting a budget

>[!IMPORTANT] Deleting a budget may remove any limits on spending, depending on your other existing budgets. For example, deleting the default $0 budget for {% data variables.product.prodname_copilot_short %} premium requests allows for unlimited usage.

{% ifversion fpt %}

As an organization owner, you can edit or delete a budget at any time, but you cannot change the budget scope.

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.billing.org-billing-menu %}

{% elsif ghec %}

You can edit or delete a budget at any time, but you cannot change the budget scope.

{% data reusables.enterprise-accounts.access-enterprise %}
{% data reusables.billing.enterprise-billing-menu %}

{% endif %}

1. Click **Budgets and alerts**.
1. To edit a budget, in the list of budgets, click {% octicon "kebab-horizontal" aria-label="View actions" %} next to the budget you want to edit, and click **{% octicon "pencil" aria-hidden="true" aria-label="pencil" %} Edit** or **{% octicon "trash" aria-hidden="true" aria-label="trash" %} Delete**.
1. Follow the prompts.
