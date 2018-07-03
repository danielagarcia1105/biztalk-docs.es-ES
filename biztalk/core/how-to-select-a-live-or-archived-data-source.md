---
title: Cómo seleccionar un origen de datos activos o archivados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83f034a41fffa0c646b0173e8b889c20373760ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967157"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>Cómo seleccionar un origen de datos activo o archivado
BizTalktracking permite obtener acceso a los datos archivados y dinámicos. Seleccione un origen de datos activo o archivado en la página principal **administración de BizTalk Server** nodo consola de administración de BizTalk Server.  El origen predeterminado son los datos activos, que se recuperan de la base de datos de administración de BizTalk. Si decide utilizar datos archivados, deberá seleccionar los servidores y bases de datos apropiados con los que desee trabajar.  

-   Los datos archivados: analizar datos archivados permite examinar tendencias tanto en su empresa en el sistema, puesto que pueden ser anteriores como sea necesario. Si selecciona datos archivados, debe seleccionar también los correspondientes servidores y bases de datos de SQL Server que contienen los datos archivados.  

     Los datos archivados se designan al seleccionar **conectarse a una base de datos de seguimiento existente...** .  

-   Datos en directo: analizar datos activos permite supervisar orquestaciones y canalizaciones, para que pueda identificar y corregir problemas en el desarrollo o entorno de ensayo. Supervisar datos activos permite también corregir problemas del sistema, tal como por qué se suspenden los mensajes.  

     Datos activos se designan al seleccionar **conectarse a un grupo existente...** .  

## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.  

### <a name="to-select-live-data"></a>Para seleccionar datos activos  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. Haga clic en el método main **administración de BizTalk Server** nodo.  

3. Haga clic en **conectarse a un grupo existente...**  

4. En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.  

5. En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.  

6. Haga clic en **Aceptar**.  

### <a name="to-select-archived-data"></a>Para seleccionar datos archivados  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. Haga clic en el método main **administración de BizTalk Server** nodo.  

3. Haga clic en **conectarse a una base de datos de seguimiento existente...**  

4. En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.  

5. En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.  

6. Haga clic en **Aceptar**.
