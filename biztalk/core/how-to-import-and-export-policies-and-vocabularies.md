---
title: "Cómo importar y exportar directivas y vocabularios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ba7cd8a9fc5d28d1b718e9a47ad6cf2f448ec7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a>Cómo importar y exportar directivas y vocabularios
Puede usar el Asistente para implementar el motor de reglas para importar o exportar una directiva o vocabulario.  
  
> [!NOTE]
>  En primer lugar deben importarse todos los vocabularios que utilicen una directiva o vocabulario o se producirá un error.  
  
### <a name="to-import-or-export-a-policy-or-vocabulary"></a>Para importar o exportar una directiva o vocabulario  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la página de bienvenida, haga clic en **siguiente**.  
  
3.  En el **la tarea de implementación** página, seleccione **Exportar directiva o vocabulario a archivo de base de datos** o **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, Haga clic en **siguiente**.  
  
4.  En el **almacén de directivas** página, en las listas desplegables, seleccione un equipo de SQL Server disponible y base de datos y, a continuación, haga clic en **siguiente**.  
  
5.  En el **Exportar directiva o vocabulario** página, realice lo siguiente y, a continuación, haga clic en **siguiente**.  
  
    1.  Seleccione **directiva** o **vocabulario** según lo desee exportar/importar.  
  
    2.  Desde el **directiva o vocabulario** lista desplegable, seleccione la directiva o vocabulario deseado.  
  
    3.  Haga clic en **examinar** para seleccionar el archivo de definición.  
  
6.  Revise el servidor, la base de datos y la información de directiva o vocabulario y, a continuación, haga clic en **siguiente**.  
  
7.  Una vez completada la importación o exportación, haga clic en **siguiente**.  
  
8.  Revisar el estado de finalización de la importación o exportación y, a continuación, haga clic en **finalizar**.