---
title: Crear un proyecto de esquema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207212"
---
# <a name="creating-a-schema-project"></a>Crear un proyecto de esquema
Para crear un proyecto de esquema:  
  
1.  En Visual Studio, cree el proyecto de BizTalk de esquema de SWIFT MX.  
  
2.  Agregue el esquema apropiado MX (descargado desde el sitio de ISO20022), que desea probar, a este proyecto.  
  
3.  Si desea ejecutar la funcionalidad de reparación de mensajes y nuevo envío para el mensaje de MX anterior, un esquema de sobre que corresponde al tipo de mensaje anterior también debe implementarse else vaya al paso 6.  
  
    > [!NOTE]
    >  Para obtener información sobre cómo generar esquemas de sobres de MX, consulte la documentación del generador de formulario.  
  
4.  Agregue el esquema de sobre para el proyecto de SWIFT MX esquema.  
  
5.  Abra el esquema de sobre en el editor de BizTalk y promocionar las propiedades "CorrelationToken" y "IsNewSubmission". Haga clic en los campos anteriores y haga clic en **promover -> promoción rápida** para promocionar estas propiedades.  
  
    > [!NOTE]
    >  Para obtener más información acerca de cómo promocionar las propiedades de un esquema, consulte la documentación de BizTalk Server.  
  
6.  Crear un archivo de clave (mediante Sn – k key.snk) y, a continuación, asigne al proyecto para crear un seguro con el nombre de ensamblado.  
  
7.  Genere e implemente el proyecto.