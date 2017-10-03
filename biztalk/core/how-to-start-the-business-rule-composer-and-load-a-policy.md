---
title: "Cómo iniciar el Compositor de reglas de negocio y cargar una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 420517c51fd6c7a6c854afe161a11a58f952db83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a>Cómo iniciar el Compositor de reglas de negocio y cargar una directiva
En esta sección se describe cómo iniciar el Compositor de reglas de negocio y cargar una directiva.  
  
### <a name="to-start-the-business-rule-composer"></a>Para iniciar el Compositor de reglas de negocio  
  
-   En el **iniciar** menú, elija **todos los programas**, señale Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
### <a name="to-load-a-policy"></a>Para cargar una directiva  
  
1.  En el Compositor de reglas de negocios, en la **almacén de reglas** menú, haga clic en **carga**.  
  
2.  En el **almacén de reglas** cuadro de diálogo, en la **SQL Server** lista desplegable, seleccione el equipo de SQL Server™ a la que desea conectarse.  
  
3.  En el **base de datos** lista desplegable, seleccione la base de datos que contiene el almacén de reglas que desea abrir.  
  
> [!NOTE]
>  La base de datos predeterminada para el almacén de reglas instalado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es **BizTalkRuleEngineDb**.  
  
> [!NOTE]
>  Si usas una cuenta de SQL Server recién creada que tenga el **exigir expiración de contraseña** y **usuario debe cambiar la contraseña en el siguiente inicio de sesión** conjunto de opciones, el Compositor de reglas de negocios no se podrá conectar a la regla Base de datos de motor.