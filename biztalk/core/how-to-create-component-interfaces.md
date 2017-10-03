---
title: "Cómo crear Interfaces de componentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-component-interfaces"></a>Cómo crear interfaces de componentes
Cree interfaces de componentes mediante la aplicación Application Designer de PeopleSoft. (Para obtener más información sobre Application Designer, vea la documentación de PeopleSoft Enterprise).  
  
 Puede agregar propiedades desde los registros de la vista del componente. En la interfaz del componente puede eliminar una propiedad que no desee que se exponga. Puede cambiar el nombre a las propiedades haciendo clic en la propiedad en cuestión y, a continuación, haciendo clic de nuevo hasta que pueda escribir un nuevo nombre. Si cambia el nombre de una propiedad, puede referirse a ella en la interfaz del componente únicamente por el nuevo nombre y no por el nombre del componente subyacente.  
  
 Las propiedades pueden tener varios iconos adjuntos. Por ejemplo, EMPLID tiene un icono que indica que es un campo clave desde el registro subyacente. NAME tiene un icono que indica que es un campo de clave alternativo desde el registro subyacente. (Para obtener una lista completa de los iconos de las propiedades, vea la documentación de PeopleBooks.)  
  
### <a name="creating-a-new-component-interface"></a>Crear una nueva interfaz de componente  
  
1.  Abra Application Designer de PeopleSoft.  
  
2.  En el menú **Archivo** , haga clic en **Nuevo**.  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  En el **New** cuadro de diálogo, seleccione **interfaz de componente**y, a continuación, haga clic en **Aceptar**.  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  En el **seleccionar el componente de origen para la interfaz de componente** ventana, seleccione el componente que usar como base para la interfaz de componente y, a continuación, haga clic en **seleccione**.  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  Si la interfaz del componente es grande, exponga las propiedades del componente de forma manual.  
  
5.  En el **Application Designer** diálogo cuadro, elija una de las siguientes opciones:  
  
    -   Haga clic en **n** para crear la interfaz de componente sin mostrar las propiedades y exponer propiedades de componente manualmente.  
  
         a. En el panel derecho, arrastre los campos correspondientes en el panel izquierdo.  
  
         b. Para seleccionar varias funciones, haga clic en el panel derecho o izquierdo, dependiendo de qué panel está activo.  
  
         Para obtener una lista completa de las funciones, vea la documentación de PeopleBooks.  
  
    -   Haga clic en **Sí** para crear la interfaz de componentes y mostrar las propiedades de la interfaz del componente subyacente.  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a>Vea también  
 [Métodos estándar en Interfaces de componentes](../core/standard-methods-in-component-interfaces.md)   
 [Apéndice C: usar Interfaces de componentes](../core/appendix-c-using-component-interfaces.md)   
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)