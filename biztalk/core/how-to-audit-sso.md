---
title: Cómo auditar SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9363df166e438aba0db89cbadd0d688c7d353a0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972085"
---
# <a name="how-to-audit-sso"></a><span data-ttu-id="82f5c-102">Cómo auditar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="82f5c-102">How to Audit SSO</span></span>
<span data-ttu-id="82f5c-103">Puede utilizar el Complemento MMC o la línea de comandos para establecer los niveles de auditoría positivo y negativo.</span><span class="sxs-lookup"><span data-stu-id="82f5c-103">You can use the MMC Snap-In or the command line to set both the positive and negative auditing levels.</span></span> <span data-ttu-id="82f5c-104">Los resultados de la auditoría se almacenan tanto en los registros de sucesos como en los de auditoría de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="82f5c-104">Results of the auditing are stored in both the event logs and the audit logs of the database.</span></span>  
  
 <span data-ttu-id="82f5c-105">Los administradores de SSO pueden establecer niveles de auditoría positivos y negativos que se ajusten a sus directivas corporativas.</span><span class="sxs-lookup"><span data-stu-id="82f5c-105">SSO administrators can set the positive and negative audit levels that suit their corporate policies.</span></span> <span data-ttu-id="82f5c-106">Puede establecer auditorías positivas y negativas en uno de los niveles siguientes:</span><span class="sxs-lookup"><span data-stu-id="82f5c-106">You can set positive and negative audits to one of the following levels:</span></span>  
  
 <span data-ttu-id="82f5c-107">0 = Ninguno</span><span class="sxs-lookup"><span data-stu-id="82f5c-107">0 = None</span></span>  
  
 <span data-ttu-id="82f5c-108">1 = Bajo</span><span class="sxs-lookup"><span data-stu-id="82f5c-108">1 = Low</span></span>  
  
 <span data-ttu-id="82f5c-109">2 = Medio</span><span class="sxs-lookup"><span data-stu-id="82f5c-109">2 = Medium</span></span>  
  
 <span data-ttu-id="82f5c-110">3 = Alto.</span><span class="sxs-lookup"><span data-stu-id="82f5c-110">3 = High.</span></span> <span data-ttu-id="82f5c-111">Este nivel ejecuta todos los mensajes de auditoría posibles.</span><span class="sxs-lookup"><span data-stu-id="82f5c-111">This level issues as many audit messages as possible.</span></span>  
  
 <span data-ttu-id="82f5c-112">El valor predeterminado para la auditoría positiva es 0 (ninguno) y para la auditoría negativa, 1 (bajo).</span><span class="sxs-lookup"><span data-stu-id="82f5c-112">The default value for positive auditing is 0 (none), and the default value for negative auditing is 1(low).</span></span>  
  
 <span data-ttu-id="82f5c-113">Para modificar la auditoría del nivel de base de datos, debe actualizar la base de datos de SSO mediante un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="82f5c-113">To change the database level auditing, you must update the SSO database using an XML file.</span></span> <span data-ttu-id="82f5c-114">Un ejemplo de archivo XML para actualizar la base de datos de SSO es:</span><span class="sxs-lookup"><span data-stu-id="82f5c-114">A sample XML file for updating the SSO database is:</span></span>  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="82f5c-115">Para auditar el inicio de sesión único con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="82f5c-115">To audit Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="82f5c-116">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-116">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="82f5c-117">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="82f5c-117">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="82f5c-118">Haga clic en **sistema**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-118">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="82f5c-119">En el **las propiedades del sistema** cuadro de diálogo, haga clic en el **auditorías** ficha.</span><span class="sxs-lookup"><span data-stu-id="82f5c-119">On the  **System Properties** dialog box, click the **Audits** tab.</span></span>  
  
5.  <span data-ttu-id="82f5c-120">Especifique la configuración adecuada y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-120">Enter the appropriate settings, and click **OK**.</span></span>  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a><span data-ttu-id="82f5c-121">Para auditar el inicio de sesión único con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="82f5c-121">To audit Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="82f5c-122">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-122">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="82f5c-123">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="82f5c-123">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="82f5c-124">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="82f5c-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="82f5c-125">Tipo **ssoconfig-auditlevel \<positivo\>\<negativo\>**, donde **\<positivo\>** es el nivel de Cuando las acciones se realizan correctamente, la auditoría y **\<negativo\>** es el nivel de auditoría de las acciones no.</span><span class="sxs-lookup"><span data-stu-id="82f5c-125">Type **ssoconfig –auditlevel \<positive\>\<negative\>**, where **\<positive\>** is the level of auditing when actions succeed, and **\<negative\>** is the level of auditing when actions fail.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82f5c-126">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="82f5c-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-audit-the-sso-database"></a><span data-ttu-id="82f5c-127">Para auditar la base de datos de SSO</span><span class="sxs-lookup"><span data-stu-id="82f5c-127">To audit the SSO database</span></span>  
  
1. <span data-ttu-id="82f5c-128">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="82f5c-129">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="82f5c-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="82f5c-130">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="82f5c-130">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="82f5c-131">Tipo **ssomanage – updatedb \<archivo de actualización\>**, donde  <strong>\<archivo de actualización\></strong>es la ruta de acceso y nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="82f5c-131">Type **ssomanage –updatedb \<update file\>**, where <strong>\<update file\></strong>is the path and name of the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="82f5c-132">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="82f5c-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f5c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="82f5c-133">See Also</span></span>  
 <span data-ttu-id="82f5c-134">[Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="82f5c-134">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="82f5c-135">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="82f5c-135">Using SSO</span></span>](../core/using-sso.md)