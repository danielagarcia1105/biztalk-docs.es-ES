---
title: Nombre de la aplicación afiliada necesaria no se especifica | Documentos de Microsoft
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
ms.openlocfilehash: 1c5ecbbcc1a1df97da5339118de873391a5d3ec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268468"
---
# <a name="required-affiliate-application-name-not-specified"></a>Nombre de aplicación afiliada necesaria no especificado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Nombre de aplicación afiliada necesaria no especificado.|  
  
## <a name="explanation"></a>Explicación  
 **Use Single Sign-On** se ha seleccionado la opción pero no se ha especificado el nombre de la aplicación afiliada.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el nombre de aplicación afiliada.  
  
#### <a name="to-configure-the-affiliate-application-name"></a>Para configurar el nombre de aplicación afiliada  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones de BizTalk**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** lista, seleccione **WCF-Custom**.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha.  
  
9. En el **las credenciales de nombre de usuario** sección, especifique un valor para **aplicación afiliada**.  
  
 Para obtener más información acerca de cómo crear una aplicación afiliada SSO, vea [http://go.microsoft.com/fwlink/?LinkId=94347](http://go.microsoft.com/fwlink/?LinkId=94347)