---
title: Cómo iniciar el Compositor de reglas de negocio y cargar una directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56d3d2c1dde771d86f8de345d6e3b249ab394b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977053"
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a>Cómo iniciar el Compositor de reglas de negocio y cargar una directiva
En esta sección se describe cómo iniciar el Compositor de reglas de negocio y cargar una directiva.  
  
### <a name="to-start-the-business-rule-composer"></a>Para iniciar el Compositor de reglas de negocio  
  
- En el **iniciar** menú, elija **todos los programas**, señale Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **compositor**.  
  
  > [!NOTE]
  >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
### <a name="to-load-a-policy"></a>Para cargar una directiva  
  
1.  En el Compositor de reglas de negocio, en el **regla Store** menú, haga clic en **carga**.  
  
2.  En el **regla Store** cuadro de diálogo el **SQL Server** lista desplegable, seleccione el equipo SQL Server™ a la que desea conectarse.  
  
3.  En el **base de datos** lista desplegable, seleccione la base de datos que contiene el almacén de reglas que desea abrir.  
  
> [!NOTE]
>  La base de datos predeterminada para el almacén de reglas que se instala de forma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es **BizTalkRuleEngineDb**.  
> 
> [!NOTE]
>  Si usa una cuenta de SQL Server recién creada que tenga el **exigir expiración de contraseña** y **usuario debe cambiar la contraseña en el siguiente inicio de sesión** conjunto de opciones, el Compositor de reglas de negocios se podrá conectar a la regla Base de datos del motor.