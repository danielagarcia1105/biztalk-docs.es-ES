---
title: "Cómo configurar el seguimiento de un esquema | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15cb2210062901786b179ec75fe3880dea660b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-schema"></a>Cómo configurar el seguimiento de un esquema
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de un esquema. Para configurar el seguimiento, especifique las propiedades de los mensajes que desee ver en las vistas de consulta de la página Concentrador de grupo de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para obtener más información sobre cómo crear y usar las consultas, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md). Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Si desea ver sólo opciones de seguimiento, puede iniciar la sesión como un miembro del grupo de operadores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-a-schema"></a>Para configurar el seguimiento de un esquema  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el esquema para el que desea configurar el seguimiento y, a continuación, expanda la aplicación que contiene el esquema.  
  
3.  Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **propiedades**.  
  
4.  En el panel izquierdo, haga clic en **seguimiento**.  
  
5.  Realice una de las siguientes acciones para especificar las propiedades que se usará para el seguimiento de mensajes y, a continuación, haga clic en **Aceptar**:  
  
    -   Seleccione el **seleccionar todas las propiedades de mensaje** casilla de verificación para utilizar todas las propiedades enumeradas.  
  
        > [!NOTE]
        >  Esta casilla solo está disponible para los esquemas que contienen propiedades promocionadas.  
  
    -   Seleccione la casilla de verificación para cada una de las propiedades que quiera utilizar.  
  
        > [!NOTE]
        >  Esto solo está disponible para los esquemas que contienen propiedades promocionadas.  
  
> [!NOTE]
>  Debería seleccionar sólo las opciones que necesita ya que el seguimiento de mensajes produce una sobrecarga de rendimiento y almacenamiento para su sistema.  
  
## <a name="see-also"></a>Vea también  
 [Administrar esquemas](../core/managing-schemas.md)