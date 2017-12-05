---
title: "Cómo habilitar el cifrado entre Analysis Services y la base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61784be74d93753b8c3ca8ecf7302c6517a1d9c4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="f0ebe-102">Cómo habilitar el cifrado entre los servicios de análisis y la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="f0ebe-102">How to Enable Encryption Between Analysis Services and the BAM Primary Import Database</span></span>
<span data-ttu-id="f0ebe-103">El cifrado no se habilita de forma predeterminada durante una instalación o actualización de BAM.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-103">Encryption is not enabled by default during an installation or upgrade of BAM.</span></span> <span data-ttu-id="f0ebe-104">Para habilitar el cifrado, deberá definir la marca UseEncryption del archivo XML de configuración de BAM con el valor 1.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-104">To enable encryption, you must set the UseEncryption flag in the BAM configuration XML file to a value of 1.</span></span>  
  
 <span data-ttu-id="f0ebe-105">También deberá habilitar el cifrado en los servicios de análisis de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-105">You must also enable encryption in SQL Server Analysis Services.</span></span> <span data-ttu-id="f0ebe-106">Para obtener más información acerca de cómo habilitar el cifrado, vea [proteger la comunicación del cliente con una instancia de Analysis Services](http://go.microsoft.com/fwlink/?LinkId=190805) (http://go.microsoft.com/fwlink/?LinkId=190805).</span><span class="sxs-lookup"><span data-stu-id="f0ebe-106">For more information about enabling encryption, see [Securing Client Communication with an Analysis Services Instance](http://go.microsoft.com/fwlink/?LinkId=190805) (http://go.microsoft.com/fwlink/?LinkId=190805).</span></span>  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="f0ebe-107">Para habilitar el cifrado entre SQL Server Analysis Services y la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="f0ebe-107">To enable encryption between SQL Server Analysis Services and the BAM Primary Import Database</span></span>  
  
1.  <span data-ttu-id="f0ebe-108">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="f0ebe-109">Navegue a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0ebe-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3.  <span data-ttu-id="f0ebe-110">Tipo de **bm get-config - FileName:\<archivo de salida\>**.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-110">Type **bm get-config -FileName:\<output file\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0ebe-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="f0ebe-112">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-112">Press **ENTER**.</span></span>  
  
5.  <span data-ttu-id="f0ebe-113">En un editor de texto, abra el archivo de configuración que ha exportado, y cambie a 1 el valor de la marca de propiedad UseEncryption.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-113">Open the file configuration file that you have exported in a text editor and change the value of the UseEncryption property flag to 1.</span></span>  
  
    -   <span data-ttu-id="f0ebe-114">Valor predeterminado: \<nombre de propiedad = "UseEncryption"\>0 \< /Property\></span><span class="sxs-lookup"><span data-stu-id="f0ebe-114">Default Setting: \<Property Name="UseEncryption"\>0\</Property\></span></span>  
  
    -   <span data-ttu-id="f0ebe-115">Nueva configuración: \<nombre de propiedad = "UseEncryption"\>1 \< /Property\></span><span class="sxs-lookup"><span data-stu-id="f0ebe-115">New Setting: \<Property Name="UseEncryption"\>1\</Property\></span></span>  
  
6.  <span data-ttu-id="f0ebe-116">Actualizar la configuración de BAM escribiendo **bm update-config - FileName:\<el archivo de configuración\>**.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-116">Update the BAM configuration by typing **bm update-config -FileName:\<config file\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0ebe-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f0ebe-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ebe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0ebe-118">See Also</span></span>  
 [<span data-ttu-id="f0ebe-119">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="f0ebe-119">BAM Management Utility</span></span>](../core/bam-management-utility.md)