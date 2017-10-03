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
# <a name="business-rules-framework-security"></a>Seguridad del marco de trabajo de reglas de negocios
El motor de reglas de negocios opera en el contexto de seguridad de la aplicación host. La identidad de la instancia de motor de reglas durante la ejecución es que del contexto del subproceso que invoca el **Policy.Execute** método.  
  
## <a name="default-security-configuration"></a>Configuración de seguridad predeterminada  
 Cuando se instala Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], dos grupos de Microsoft Windows se crean de forma predeterminada, uno para administradores y otro para usuarios: "Administradores de BizTalk Server" y "Usuarios de aplicación de BizTalk". Estos dos grupos de Windows son miembros de los roles BTS_ADMIN_USERS y BTS_HOST_USERS SQL que son, a su vez, miembros de los roles RE_ADMIN_USERS y RE_HOST_USERS SQL respectivamente.  
  
 Los roles SQL predeterminados se crean cada vez que se crea un almacén de reglas: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS y RE_HOST_USERS.  
  
|Grupos de Windows predeterminados|funciones SQL|  
|----------------------------|---------------|  
|Administradores de servidor BizTalk Server|RE_ADMIN_USERS|  
|Usuarios de aplicación de BizTalk|RE_HOST_USERS|  
  
 Solo los usuarios del rol RE_ADMIN_USERS pueden ejecutar los procedimientos almacenados que actualizan las tablas de configuración de protección de acceso de implementación y entidad. Esto quiere decir que la configuración de protección, implementación y anulación de implementación solo las efectúan los administradores del motor de reglas. Los usuarios del rol RE_HOST_USERS pueden ejecutar el resto de procedimientos almacenados en el almacén de reglas SQL.  
  
 Independientemente del orden de instalación del motor de reglas, el proceso de configuración del motor de reglas concede al rol RE_HOST_USERS SQL la pertenencia a la cuenta de Servicio de actualización del motor de reglas, si todavía no tiene acceso a la base de datos. Sin embargo, si el motor de reglas se ha instalado después de la instalación inicial de BizTalk, el grupo de usuarios BizTalk, específico del host, no se agrega al rol BTS_HOST_USERS SQL en la base de datos del motor de reglas, porque la creación del host ya se ha completado. Será necesario realizar este paso manualmente.  
  
## <a name="artifact-level-security"></a>Seguridad de nivel de artefactos  
 Además de la configuración de seguridad predeterminada, el motor de reglas de negocios también pueden proporcionar seguridad en el artefacto: nivel de directivas y vocabularios.  
  
 Todas las versiones de directivas o vocabularios tienen uno o más grupos de autorización asociados. Un grupo de autorización es una lista con nombres de usuarios de Microsoft Windows, usuarios de SQL, roles SQL y grupos de Windows, con un nivel de acceso particular en cada tipo.  
  
 Cuando se crea una nueva directiva o un nuevo vocabulario en el almacén de reglas, solo el usuario que lo creó y el administrador del motor de reglas tienen accesos de lectura/ejecución y de modificación/eliminación de forma predeterminada. El Administrador de motor de reglas puede configurar qué usuarios (los procesos funcionan con las credenciales de usuario) tienen el nivel de acceso, o derechos, para realizar diferentes operaciones — lectura/ejecución, modificar o eliminar, permisos completos o sin permiso.  
  
 La seguridad específica de artefactos no está habilitada de forma predeterminada. La configuración de seguridad a nivel de artefactos no está disponible actualmente mediante la interfaz de usuario. No obstante, se puede establecer mediante programación con la credencial de administrador del motor de reglas de negocios. En el siguiente fragmento de código se muestra cómo crear una nueva autorización y cómo asociar un grupo a un conjunto de reglas.  
  
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
>  La utilización de seguridad de artefactos de nivel 1 puede disminuir el rendimiento, porque la directiva tendrá que efectuar una búsqueda en la base de datos con cada ejecución para evaluar el nivel de acceso de las aplicaciones antes de devolver una instancia del motor de reglas.  
  
## <a name="see-also"></a>Vea también  
 [Notas de seguridad importante para el motor de reglas de negocios](../core/important-security-notes-for-the-business-rule-engine.md)