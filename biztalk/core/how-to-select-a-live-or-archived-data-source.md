---
title: "Cómo seleccionar un origen de datos activos o archivados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7172a822a71e2b0d7dc621e6c1e11b055b723bd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>Cómo seleccionar un origen de datos activo o archivado
BizTalktracking permite obtener acceso a los datos archivados y dinámicos. Seleccione un origen de datos activos o archivados en la página principal **administración de BizTalk Server** nodo consola de administración de BizTalk Server.  El origen predeterminado son los datos activos, que se recuperan de la base de datos de administración de BizTalk. Si decide utilizar datos archivados, deberá seleccionar los servidores y bases de datos apropiados con los que desee trabajar.  
  
-   Los datos archivados: analizar datos archivados permite examinar tendencias tanto en su empresa como en el sistema, puesto que pueden ser anteriores como sea necesario. Si selecciona datos archivados, debe seleccionar también los correspondientes servidores y bases de datos de SQL Server que contienen los datos archivados.  
  
     Los datos archivados se designan al seleccionar **conectar a una base de datos de seguimiento existente...** .  
  
-   Datos activos: analizar datos activos permite supervisar orquestaciones y canalizaciones, para que pueda identificar y corregir problemas en el desarrollo o el entorno de ensayo. Supervisar datos activos permite también corregir problemas del sistema, tal como por qué se suspenden los mensajes.  
  
     Datos activos se designan al seleccionar **conectar a un grupo existente...** .  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-select-live-data"></a>Para seleccionar datos activos  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Haga clic en el método main **administración de BizTalk Server** nodo.  
  
3.  Haga clic en **conectar a un grupo existente...**  
  
4.  En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.  
  
5.  En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.  
  
6.  Haga clic en **Aceptar**.  
  
### <a name="to-select-archived-data"></a>Para seleccionar datos archivados  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Haga clic en el método main **administración de BizTalk Server** nodo.  
  
3.  Haga clic en **conectar a una base de datos de seguimiento existente...**  
  
4.  En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.  
  
5.  En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.  
  
6.  Haga clic en **Aceptar**.