---
title: CLI example- Enable BYOK TDE - Azure SQL Database Managed Instance
description: "Learn how to configure an Azure SQL Managed Instance to start using BYOK Transparent Data Encryption (TDE) for encryption-at-rest using PowerShell."
services: sql-database
ms.service: sql-database
ms.subservice: security
ms.custom: 
ms.devlang: azurecli
ms.topic: conceptual
author: MladjoA
ms.author: mlandzic
ms.reviewer: vanto, carlrab
ms.date: 11/05/2019
---
# Manage Transparent Data Encryption in a Managed Instance using your own key from Azure Key Vault

This Azure CLI script example configures Transparent Data Encryption (TDE) with customer-managed key for Azure SQL Managed Instance, using a key from Azure Key Vault. This is often referred to as a Bring Your Own Key scenario for TDE. To learn more about the TDE with customer-managed key, see [TDE Bring Your Own Key to Azure SQL](../transparent-data-encryption-byok-azure-sql.md).

## Prerequisites

- An existing Managed Instance. See [Use Azure CLI to create an Azure SQL Database managed instance](sql-database-create-configure-managed-instance-cli.md).

If you choose to install and use the CLI locally, this article requires that you are running the Azure CLI version 2.0 or later. Run `az --version` to find the version. If you need to install or upgrade, see [Install the Azure CLI](/cli/azure/install-azure-cli).

## Sample script

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

### Sign in to Azure

```azurecli-interactive
$subscription = "<subscriptionId>" # add subscription here

az account set -s $subscription # ...or use 'az login'
```

### Run the script

[!code-azurecli-interactive[main](../../../cli_scripts/sql-database/transparent-data-encryption/setup-tde-byok-sqlmi.sh "Set up BYOK TDE for SQL Managed Instance")]

### Clean up deployment

Use the following command to remove the resource group and all resources associated with it.

```azurecli-interactive
az group delete --name $resource
```

## Script explanation

This script uses the following commands. Each command in the table links to command specific documentation.

| Command | Notes |
|---|---|
| [az sql db create](/cli/azure/sql/db?view=azure-cli-latest) | Creates a database. |
| [az sql failover-group create](/cli/azure/sql/failover-group?view=azure-cli-latest#az-sql-failover-group-create) | Creates a failover group. |

## Next steps

For more information on the Azure CLI, see [Azure CLI documentation](/cli/azure).

Additional SQL Database CLI script samples can be found in the [Azure SQL Database documentation](../sql-database-cli-samples.md).
