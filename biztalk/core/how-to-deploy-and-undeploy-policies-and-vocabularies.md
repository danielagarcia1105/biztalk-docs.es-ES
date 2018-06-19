---
title: Cómo implementar y anular la implementación de directivas y vocabularios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef36df71459935b588f54c1dadc30ab02a7e722e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249572"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a>Cómo implementar y anular la implementación de directivas y vocabularios
Puede utilizar el Asistente para implementar el motor de reglas para implementar o anular la implementación de una directiva.  
  
 En el Asistente para implementar el motor de reglas, cuando intenta implementar, sólo se muestran en la lista desplegable las versiones de directivas publicadas. Cuando intenta anular una implementación, sólo se muestran en la lista desplegable las versiones de directivas implementadas.  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>Para implementar o anular la implementación de una directiva  
  
1.  Haga clic en **iniciar**, seleccione **archivos de programa**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **Asistente para implementación de motor de reglas** página de bienvenida, haga clic en **siguiente**.  
  
3.  Seleccione **implementar Directiva** o **anular la implementación de directiva**y, a continuación, haga clic en **siguiente**.  
  
4.  En las listas desplegables, seleccione un equipo de SQL Server disponible y la base de datos y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Sólo puede implementar en la base de datos del almacén de reglas en la que se ha configurado. Cualquier intento de realizar una implementación en una base de datos diferente generará un error.  
  
5.  En la lista desplegable, seleccione una directiva y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Cuando intenta implementar, sólo se muestran en la lista desplegable las versiones de directivas publicadas. Cuando intenta anular una implementación, sólo se muestran en la lista desplegable las versiones de directivas implementadas.  
  
6.  Revise el servidor, la base de datos y la información de la directiva y, a continuación, haga clic en **siguiente**.  
  
7.  Observe el progreso de la implementación o de la anulación de la implementación. Cuando haya finalizado, haga clic en **siguiente**.  
  
8.  Revise el estado de finalización de la implementación o anulación de implementación y, a continuación, haga clic en **finalizar**.  
  
> [!NOTE]
>  También puede implementar o anular la implementación de una versión de directiva en el Compositor de reglas de negocio haciendo clic en la versión de directiva y, a continuación, haga clic en **implementar** o **anular la implementación**.