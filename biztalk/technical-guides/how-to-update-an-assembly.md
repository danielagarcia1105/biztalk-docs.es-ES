---
title: "Cómo actualizar un ensamblado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163b06706652b1f65b9a76e3feea8911a2ca4c88
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-an-assembly"></a>Cómo actualizar un ensamblado
En este tema se describe cómo actualizar la versión de un ensamblado y la aplicación que se implementa un ensamblado al uso de Visual Studio 2010.  
  
> [!NOTE]  
>  Si va a actualizar un ensamblado con una nueva versión, no es preciso reiniciar la aplicación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.  
  
## <a name="updating-an-assembly"></a>Actualizar un ensamblado  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a>Para incrementar el número de versión de un ensamblado  
  
1.  En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en el **aplicación** ficha.  
  
3.  En el panel derecho, haga clic en **información de ensamblado**.  
  
4.  En el **información de ensamblado** diálogo cuadro, especifique valores para la **versión del ensamblado** campo para aumentar el número de versión de ensamblado. Incremente únicamente el número principal o secundario de la versión. El número de versión principal es el primer dígito en la secuencia (***n***. 0.0.0); el número de versión secundaria es el segundo dígito en la secuencia (0. ***n*** . 0.0). BizTalk Server no reconocerá un cambio de número de versión que está más adelante en la secuencia, como 0,0.  ***n*** .0 ó 0.0.0. ***n***.  
  
5.  Haga clic en **Aceptar** para cerrar el **información de ensamblado** cuadro de diálogo.  
  
6.  Guarde el proyecto.  
  
    > [!NOTE]  
    >  Utilice el Diseñador de canalizaciones y el Modelo de objetos para el explorador de BizTalk para evitar conflictos entre los esquemas al incrementar las versiones de los ensamblados.  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a>Para cambiar la aplicación que se implementa un ensamblado  
  
1.  En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en el **implementación** ficha.  
  
3.  En el panel derecho, especifique el nombre de aplicación en el **nombre de la aplicación** campo.  
  
4.  Asegúrese de que el **instalar en la caché Global de ensamblados** propiedad está establecida en **True**.  
  
    > [!NOTE]  
    >  Al implementar la solución, los ensamblados se implementarán en la nueva aplicación y se instalarán en la GAC.