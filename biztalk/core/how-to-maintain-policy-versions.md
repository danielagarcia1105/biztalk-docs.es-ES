---
title: "Cómo mantener versiones de directivas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-policy-versions"></a>Cómo mantener versiones de directivas
Después de agregar reglas a una versión de la directiva, puede guardar la versión en el almacén de reglas para su posterior desarrollo, o puede publicarla para crear un conjunto de reglas bien definido e inmutable que pueda ser implementado para su utilización en una aplicación basada en reglas.  
  
 Este tema contiene procedimientos para las siguientes tareas:  
  
-   Para crear una nueva versión vacía de una directiva  
  
-   Para guardar una versión de directiva  
  
-   Para publicar una versión de directiva  
  
-   Para crear una versión actualizada de una directiva  
  
-   Para actualizar una directiva de modo que use un ensamblado actualizado  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a>Para crear una nueva versión vacía de una directiva  
  
-   Haga clic en la carpeta de directiva y, a continuación, haga clic en **agregar nueva versión**.  
  
### <a name="to-save-a-policy-version"></a>Para guardar una versión de directiva  
  
-   Haga clic en la versión de directiva y, a continuación, haga clic en **guardar**.  
  
### <a name="to-publish-a-policy-version"></a>Para publicar una versión de directiva  
  
-   Haga clic en la versión de directiva y, a continuación, haga clic en **publicar**.  
  
### <a name="to-create-an-updated-version-of-a-policy"></a>Para crear una versión actualizada de una directiva  
  
1.  Haga clic en una versión de directiva existente y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en la carpeta de directiva y, a continuación, haga clic en **pegar**.  
  
     Se crea una nueva versión, con los mismos elementos que la versión copiada.  
  
    > [!NOTE]
    >  Si la directiva utiliza un ensamblado .NET y éste se actualiza, debe enlazar la directiva con la nueva versión del ensamblado.  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a>Para actualizar una directiva de modo que use un ensamblado actualizado  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**, seleccione **configuración de .NET Framework**y, a continuación, haga clic en **ensamblados configurados** .  
  
2.  Vaya a propiedades del ensamblado de destino y haga clic en el **directiva de enlace** ficha.  
  
3.  En la caché de ensamblados global, cambie el número de versión a una versión más reciente.  
  
    > [!NOTE]
    >  Todos los ensamblados que utilizan las directivas deben agregarse a la caché de ensamblados global.