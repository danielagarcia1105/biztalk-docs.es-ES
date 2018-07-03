---
title: Conectarse a las columnas de SQL Server Always Encrypted con BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fd02a1c89b3c308fc853dde8b541d23aa999053
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008557"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a><span data-ttu-id="87caa-102">Conectarse a las columnas de SQL Server Always Encrypted con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="87caa-102">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>
<span data-ttu-id="87caa-103">Habilitar Always Encrypted en el adaptador de WCF-SQL [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] para consultar columnas cifradas.</span><span class="sxs-lookup"><span data-stu-id="87caa-103">Enable Always Encrypted in the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to query encrypted columns.</span></span>  

<span data-ttu-id="87caa-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , el adaptador de WCF-SQL puede consultar columnas cifradas en [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87caa-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the WCF-SQL adapter can query encrypted columns in [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="87caa-105">El `ColumnEncryptionSetting` enlaza la propiedad se utiliza para habilitar o deshabilitar la funcionalidad para obtener los valores de columna cifrado/descifrado de una base de datos Always Encrypted.</span><span class="sxs-lookup"><span data-stu-id="87caa-105">The `ColumnEncryptionSetting` binding property is used to enable or disable the functionality to get decrypted/encrypted column values from an Always Encrypted database.</span></span>

<span data-ttu-id="87caa-106">Este tema muestra cómo habilitar o deshabilitar esta característica en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87caa-106">This topic shows you how to enable or disable this feature in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

> [!TIP]
> <span data-ttu-id="87caa-107">[Always Encrypted (motor de base de datos)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) es un excelente recurso para comprender y obtener más información sobre esto [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] característica.</span><span class="sxs-lookup"><span data-stu-id="87caa-107">[Always Encrypted (Database Engine)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) is a great resource to understand and learn more about this [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] feature.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87caa-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="87caa-108">Prerequisites</span></span>
<span data-ttu-id="87caa-109">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87caa-109">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="enable-always-encrypted"></a><span data-ttu-id="87caa-110">Habilitar Always Encrypted</span><span class="sxs-lookup"><span data-stu-id="87caa-110">Enable Always Encrypted</span></span>

1. <span data-ttu-id="87caa-111">En el **administración de BizTalk Server** de consola, haga clic en el puerto de WCF-SQL y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="87caa-111">In the **BizTalk Server Administration** console, right-click your WCF-SQL port, and select **Properties**.</span></span>
2. <span data-ttu-id="87caa-112">Vaya a la **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="87caa-112">Go to the **Binding** tab.</span></span>
3. <span data-ttu-id="87caa-113">En **Always Encrypted**, habilitar o deshabilitar la `ColumnEncryptionSettings` propiedad:</span><span class="sxs-lookup"><span data-stu-id="87caa-113">Under **Always Encrypted**, enable or disable the `ColumnEncryptionSettings` property:</span></span>

* <span data-ttu-id="87caa-114">**Habilitado**: las consultas de puerto y obtiene los datos cifrados de una base de datos Always Encrypted</span><span class="sxs-lookup"><span data-stu-id="87caa-114">**Enabled**: The port queries, and gets encrypted data from an Always Encrypted database</span></span>
* <span data-ttu-id="87caa-115">**Deshabilitado**: el puerto de consulta a la base de datos Always Encrypted, pero los datos devueltos se aplica un algoritmo hash</span><span class="sxs-lookup"><span data-stu-id="87caa-115">**Disabled**: The port queries the Always Encrypted database, but the data returned is hashed</span></span>

    ![Habilitar Always Encrypted](../core/media/enable-always-encrypted.png)

4. <span data-ttu-id="87caa-117">Seleccione **aplicar**, y **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="87caa-117">Select **Apply**, and **OK** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="87caa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="87caa-118">See also</span></span>
[<span data-ttu-id="87caa-119">Always Encrypted (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="87caa-119">Always Encrypted (Database Engine)</span></span>](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[<span data-ttu-id="87caa-120">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="87caa-120">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)