---
title: Seguridad de marco de trabajo de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, code samples
- security, business rules
- artifacts, security
- security, artifacts
- business rules, security
ms.assetid: 86582d3a-259e-47f2-9f72-8dbbe0051503
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2c3a38190d242c85b134a791a8c2cd05c208050
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-framework-security"></a><span data-ttu-id="524c9-102">Seguridad del marco de trabajo de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="524c9-102">Business Rules Framework Security</span></span>
<span data-ttu-id="524c9-103">El motor de reglas de negocios opera en el contexto de seguridad de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="524c9-103">The Business Rule Engine operates in the security context of the hosting application.</span></span> <span data-ttu-id="524c9-104">La identidad de la instancia de motor de reglas durante la ejecución es que del contexto del subproceso que invoca el **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="524c9-104">The identity of the rule engine instance during execution is that of the thread context that invokes the **Policy.Execute** method.</span></span>  
  
## <a name="default-security-configuration"></a><span data-ttu-id="524c9-105">Configuración de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="524c9-105">Default security configuration</span></span>  
 <span data-ttu-id="524c9-106">Cuando se instala Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], dos grupos de Microsoft Windows se crean de forma predeterminada, uno para administradores y otro para usuarios: "Administradores de BizTalk Server" y "Usuarios de aplicación de BizTalk".</span><span class="sxs-lookup"><span data-stu-id="524c9-106">When you install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], two Microsoft Windows groups are created by default, one for administrators and one for users: "BizTalk Server Administrators" and "BizTalk Application Users."</span></span> <span data-ttu-id="524c9-107">Estos dos grupos de Windows son miembros de los roles BTS_ADMIN_USERS y BTS_HOST_USERS SQL que son, a su vez, miembros de los roles RE_ADMIN_USERS y RE_HOST_USERS SQL respectivamente.</span><span class="sxs-lookup"><span data-stu-id="524c9-107">These two Windows groups are members of BTS_ADMIN_USERS and BTS_HOST_USERS SQL Roles which are members of RE_ADMIN_USERS and RE_HOST_USERS SQL Roles respectively.</span></span>  
  
 <span data-ttu-id="524c9-108">Los roles SQL predeterminados se crean cada vez que se crea un almacén de reglas: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS y RE_HOST_USERS.</span><span class="sxs-lookup"><span data-stu-id="524c9-108">The default SQL roles are created whenever a rule store is created: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS and RE_HOST_USERS.</span></span>  
  
|<span data-ttu-id="524c9-109">Grupos de Windows predeterminados</span><span class="sxs-lookup"><span data-stu-id="524c9-109">Default Windows groups</span></span>|<span data-ttu-id="524c9-110">funciones SQL</span><span class="sxs-lookup"><span data-stu-id="524c9-110">SQL roles</span></span>|  
|----------------------------|---------------|  
|<span data-ttu-id="524c9-111">Administradores de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="524c9-111">BizTalk Server Administrators</span></span>|<span data-ttu-id="524c9-112">RE_ADMIN_USERS</span><span class="sxs-lookup"><span data-stu-id="524c9-112">RE_ADMIN_USERS</span></span>|  
|<span data-ttu-id="524c9-113">Usuarios de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="524c9-113">BizTalk Application Users</span></span>|<span data-ttu-id="524c9-114">RE_HOST_USERS</span><span class="sxs-lookup"><span data-stu-id="524c9-114">RE_HOST_USERS</span></span>|  
  
 <span data-ttu-id="524c9-115">Solo los usuarios del rol RE_ADMIN_USERS pueden ejecutar los procedimientos almacenados que actualizan las tablas de configuración de protección de acceso de implementación y entidad.</span><span class="sxs-lookup"><span data-stu-id="524c9-115">Only users in the RE_ADMIN_USERS role can execute the stored procedures that update the deployment and entity access protection configuration tables.</span></span> <span data-ttu-id="524c9-116">Esto quiere decir que la configuración de protección, implementación y anulación de implementación solo las efectúan los administradores del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="524c9-116">This means that the deployment, undeployment, and protection configuration are all done only by rule engine administrators.</span></span> <span data-ttu-id="524c9-117">Los usuarios del rol RE_HOST_USERS pueden ejecutar el resto de procedimientos almacenados en el almacén de reglas SQL.</span><span class="sxs-lookup"><span data-stu-id="524c9-117">Users in the RE_HOST_USERS role can execute the other stored procedures in the SQL rule store.</span></span>  
  
 <span data-ttu-id="524c9-118">Independientemente del orden de instalación del motor de reglas, el proceso de configuración del motor de reglas concede al rol RE_HOST_USERS SQL la pertenencia a la cuenta de Servicio de actualización del motor de reglas, si todavía no tiene acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="524c9-118">Regardless of the order of installation of the rule engine, the rule engine configuration process grants the Rule Engine Update Service account membership to the RE_HOST_USERS SQL role, if it does not already have database access.</span></span> <span data-ttu-id="524c9-119">Sin embargo, si el motor de reglas se ha instalado después de la instalación inicial de BizTalk, el grupo de usuarios BizTalk, específico del host, no se agrega al rol BTS_HOST_USERS SQL en la base de datos del motor de reglas, porque la creación del host ya se ha completado.</span><span class="sxs-lookup"><span data-stu-id="524c9-119">However, if the rule engine is installed after the initial BizTalk installation the BizTalk, host-specific users group is not added to the BTS_HOST_USERS SQL role in the Rule Engine database because host creation has already been completed.</span></span> <span data-ttu-id="524c9-120">Será necesario realizar este paso manualmente.</span><span class="sxs-lookup"><span data-stu-id="524c9-120">You need to perform this step manually.</span></span>  
  
## <a name="artifact-level-security"></a><span data-ttu-id="524c9-121">Seguridad de nivel de artefactos</span><span class="sxs-lookup"><span data-stu-id="524c9-121">Artifact level security</span></span>  
 <span data-ttu-id="524c9-122">Además de la configuración de seguridad predeterminada, el motor de reglas de negocios también pueden proporcionar seguridad en el artefacto: nivel de directivas y vocabularios.</span><span class="sxs-lookup"><span data-stu-id="524c9-122">In addition to the default security configuration, the Business Rule Engine can also provide security at the artifact—policy and vocabulary level.</span></span>  
  
 <span data-ttu-id="524c9-123">Todas las versiones de directivas o vocabularios tienen uno o más grupos de autorización asociados.</span><span class="sxs-lookup"><span data-stu-id="524c9-123">Each policy or vocabulary version has one or more authorization groups associated with it.</span></span> <span data-ttu-id="524c9-124">Un grupo de autorización es una lista con nombres de usuarios de Microsoft Windows, usuarios de SQL, roles SQL y grupos de Windows, con un nivel de acceso particular en cada tipo.</span><span class="sxs-lookup"><span data-stu-id="524c9-124">An Authorization group is a named list of Microsoft Windows users, SQL users, SQL roles, and Windows groups, with a particular access level on each type.</span></span>  
  
 <span data-ttu-id="524c9-125">Cuando se crea una nueva directiva o un nuevo vocabulario en el almacén de reglas, solo el usuario que lo creó y el administrador del motor de reglas tienen accesos de lectura/ejecución y de modificación/eliminación de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="524c9-125">When a new policy or vocabulary is created in the rule store, only the user who created it and the rule engine administrator have both read/execute and modify/delete access by default.</span></span> <span data-ttu-id="524c9-126">El Administrador de motor de reglas puede configurar qué usuarios (los procesos funcionan con las credenciales de usuario) tienen el nivel de acceso, o derechos, para realizar diferentes operaciones — lectura/ejecución, modificar o eliminar, permisos completos o sin permiso.</span><span class="sxs-lookup"><span data-stu-id="524c9-126">The rule engine administrator can configure which users (processes operate under user credentials) have the access level, or rights, to perform different operations—read/execute, modify/delete, full permission, or no permission.</span></span>  
  
 <span data-ttu-id="524c9-127">La seguridad específica de artefactos no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="524c9-127">Artifact specific security is not enabled by default.</span></span> <span data-ttu-id="524c9-128">La configuración de seguridad a nivel de artefactos no está disponible actualmente mediante la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="524c9-128">Setting artifact level security is not currently available through the user interface.</span></span> <span data-ttu-id="524c9-129">No obstante, se puede establecer mediante programación con la credencial de administrador del motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="524c9-129">However, it can be set programmatically with the Business Rule Engine administrator credential.</span></span> <span data-ttu-id="524c9-130">En el siguiente fragmento de código se muestra cómo crear una nueva autorización y cómo asociar un grupo a un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="524c9-130">The following code fragment shows how to create a new authorization and associate the group to a rule set.</span></span>  
  
```  
RuleSet rs;  
string RSName;     
  
// Create new user  
AuthorizationGroupEntry newuser = new AuthorizationGroupEntry(UserName, UID);  
AuthorizationGroupEntryCollection AGEC = new AuthorizationGroupEntryCollection();  
AGEC.Add(newuser);  
  
// Define new authorization group collection  
AuthorizationGroupCollection AGC = new AuthorizationGroupCollection();  
  
// Create new authorization group  
AuthorizationGroup AG = new AuthorizationGroup(GroupName, AccessPermit, AGEC);  
  
//add the authorization group to the authorization group collection  
AGC.Add(AG);  
  
//saving the authorization group collection to the rule store  
m_sqlRS.SaveAuthorizationGroups(AGC);  
  
rs = m_sqlRS.GetRuleSet(rsInfo[0]);                 
RSName = rs.Name;  
  
// Associate authorization group to the ruleset  
m_sqlRS.SetRuleSetAuthorizations(RSName, AGC);  
  
// Get ruleset by name from SQL rule store  
RuleSetInfoCollection rsInfo = m_sqlRS.GetRuleSets("myRuleSet", RuleStore.Filter.All);  
```  
  
> [!NOTE]
>  <span data-ttu-id="524c9-131">La utilización de seguridad de artefactos de nivel 1 puede disminuir el rendimiento, porque la directiva tendrá que efectuar una búsqueda en la base de datos con cada ejecución para evaluar el nivel de acceso de las aplicaciones antes de devolver una instancia del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="524c9-131">The use of artifact level l security can diminish performance, because the policy will have to do a database lookup on each execution to evaluate the application's access level before returning an instance of the rule engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524c9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="524c9-132">See Also</span></span>  
 [<span data-ttu-id="524c9-133">Notas de seguridad importante para el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="524c9-133">Important Security Notes for the Business Rule Engine</span></span>](../core/important-security-notes-for-the-business-rule-engine.md)