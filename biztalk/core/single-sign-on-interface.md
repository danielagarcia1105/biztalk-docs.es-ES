---
title: Inicio de sesión de la interfaz de único | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2e3c2d3-a7e9-4a45-965d-bfe4bf200c34
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee479a29a424228b31bc3fcd5752f8da7cc3ce28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276796"
---
# <a name="single-sign-on-interface"></a>Interfaz de inicio de sesión único

## <a name="interfaces"></a>Interfaces
En la tabla siguiente se describen las interfaces COM y .NET Framework que conforman la interfaz de inicio de sesión único.  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin|ISSOAdmin (interfaz) (COM)|Crea, actualiza y elimina una aplicación de SSO. También realiza otras funciones administrativas.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore|ISSOConfigStore (interfaz) (COM)|Obtiene y establece información en el almacén de configuración SSO.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1|ISSOLookup1 (interfaz) (COM)|Le permite buscar las credenciales externas de una aplicación especificada para el usuario actual.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2|ISSOLookup2 (interfaz) (COM)|Igual que la interfaz anterior, pero también le permite buscar las credenciales de Windows para un usuario externo especificado.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper|Interfaz ISSOMapper (COM)|Le permite establecer las credenciales externas del usuario actual de una aplicación especificada.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping|ISSOMapping (interfaz) (COM)|Crea y mantiene la asignación entre usuarios y aplicaciones afiliadas.|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket|ISSOTicket (interfaz) (COM)|Crea el vale que contiene la información de seguridad adecuada. A continuación, se envía el vale con el mensaje apropiado desde su aplicación.|  


## <a name="password-sync-helper"></a>Aplicación auxiliar de sincronización de contraseñas  
 Además, Host Integration Server admite el componente Aplicación auxiliar de sincronización de contraseñas. La aplicación auxiliar de sincronización de contraseñas se puede utilizar para diseñar componentes de sincronización de contraseñas. En la siguiente tabla se describen las interfaces COM y .NET Framework expuestas por la aplicación auxiliar de sincronización de contraseñas.  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper|ISSONotification (interfaz) (COM)|Controla los cambios de contraseña con sistemas operativos que no sean Windows.|  
||SExternalAccount (estructura) (COM)|Describe una cuenta externa.|  
||SPasswordChange (estructura) (COM)|Describe un cambio de contraseña.|  
||SPasswordChangeComplete (estructura) (COM)|Describe la realización de un cambio de contraseña.|  
||SStatus (estructura) (COM)|Describe un error o evento.|  
||SAdapterInGroup (estructura) (COM)|Describe el adaptador de un grupo determinado.|  
||SAdapter (estructura) (COM)|Describe un adaptador específico.|

## <a name="see-also"></a>Vea también
Ver los objetos COM de SSO [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 