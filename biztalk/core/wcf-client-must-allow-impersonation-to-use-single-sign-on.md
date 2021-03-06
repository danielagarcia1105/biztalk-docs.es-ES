---
title: Cliente de WCF debe permitir la suplantación utilice Single Sign-On | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2d5ebfc9853f10417c1d2ad2c41a0d2531ff6de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971477"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a>El cliente de WCF debe permitir que la Suplantación utilice el inicio de sesión único
## <a name="details"></a>Detalles  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |           El cliente de WCF debe permitir que la Suplantación utilice el inicio de sesión único.            |

## <a name="explanation"></a>Explicación  
 El inicio de sesión único (SSO) está habilitado en la ubicación de recepción pero el cliente de WCF no permite la suplantación.  

## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que el cliente de WCF que invoca el servicio permita la suplantación.  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione **WCF-Custom** (o **WCF-CustomIsolate**).  

7. Haga clic en **configurar**.  

8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.  

9. En el **comportamiento** sección, haga clic en **ServiceAuthorization**. En el **configuración** sección, la propiedad **ImpersonateCallerForAllOperations** debe establecerse en **True**.  

10. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **otros** ficha.  

11. En las secciones credenciales, seleccione la opción **Use Single Sign-On**.
