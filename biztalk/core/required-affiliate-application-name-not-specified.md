---
title: Nombre de la aplicación afiliada necesaria no especificado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3e82a39-b052-4702-bfe2-700756a0ee6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acadd366af7616bd84e1656fe3e5d75afd3673e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015307"
---
# <a name="required-affiliate-application-name-not-specified"></a>Nombre de aplicación afiliada necesaria no especificado.
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                 Nombre de aplicación afiliada necesaria no especificado.                  |
  
## <a name="explanation"></a>Explicación  
 **Usar inicio de sesión único** se ha seleccionado la opción pero no se ha especificado el nombre de la aplicación afiliada.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el nombre de aplicación afiliada.  
  
#### <a name="to-configure-the-affiliate-application-name"></a>Para configurar el nombre de aplicación afiliada  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones de BizTalk**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione **WCF-Custom**.  
  
7. Haga clic en **configurar**.  
  
8. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha.  
  
9. En el **credenciales de nombre de usuario** , especifique un valor para **aplicación afiliada**.  
  
   Para obtener más información acerca de cómo crear un inicio de sesión único de aplicación afiliada, vea [http://go.microsoft.com/fwlink/?LinkId=94347](http://go.microsoft.com/fwlink/?LinkId=94347)