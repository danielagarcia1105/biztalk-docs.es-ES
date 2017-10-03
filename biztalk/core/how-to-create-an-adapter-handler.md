---
title: "Cómo crear un controlador de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dbd0658b43d9e042718153654a4c2666a01feb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-adapter-handler"></a>Cómo crear un controlador de adaptador
Se puede crear un controlador de adaptador de envío o recepción utilizando la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Es preciso ser miembro del grupo de administradores de inicio de sesión único para crear un controlador de adaptador.  
  
### <a name="to-create-an-adapter-handler"></a>Para crear un controlador de adaptador  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en el adaptador para el que desea agregar un envío o controlador de recepción, seleccione **New**y, a continuación, haga clic en **controlador de envío** para crear un controlador de envío o haga clic en  **Controlador de recepción** para crear un controlador de recepción.  
  
3.  En el  **\<nombre de host > propiedades** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con el que será el controlador de adaptador asociado.  
  
4.  Si va a crear un controlador de envío de adaptador, seleccione la opción de **establecer este controlador como predeterminado** si desea que sea el controlador de envío predeterminado para este adaptador.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y eliminar controladores de adaptador](../core/creating-and-deleting-adapter-handlers.md)