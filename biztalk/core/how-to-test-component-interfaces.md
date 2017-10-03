---
title: "Cómo probar Interfaces de componentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-component-interfaces"></a>Cómo comprobar interfaces de componentes
El adaptador de Microsoft BizTalk para PeopleSoft Enterprise utiliza interfaces de componentes y metadatos de PeopleSoft, lo que le permite controlar interfaces de componentes nuevas o modificadas. El adaptador no realiza suposición alguna de las interfaces de componentes; sólo asume que son lógicas y válidas. Por consiguiente, cada interfaz de componente debe comprobarse antes de que se utilice como origen para el adaptador.  
  
 Si el usuario efectúa cambios en la aplicación subyacente, o si tiene lugar una actualización de PeopleSoft, y los cambios invalidan una interfaz de componente, es obligación del usuario reparar la interfaz de componente no válida antes de que el adaptador la utilice.  
  
### <a name="to-test-a-component-interface"></a>Para comprobar una interfaz de componente  
  
1.  En el Diseñador de aplicaciones, en la **herramientas** menú, haga clic en **interfaz de componentes de prueba**.  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  En el **comprobación de la interfaz de componente** diálogo cuadro, probar la interfaz de componente utilizando uno de los métodos siguientes. Cuando termine de realizar cambios, haga clic con el botón secundario en el elemento superior del panel.  
  
    > [!NOTE]
    >  Si fuera necesario, haga clic en el cuadro de diálogo para que pase a primer plano.  
  
    -   Para probar la interfaz de componente con el método de búsqueda, haga clic en **buscar**.  
  
         El **evaluador de interfaz de componente: resultados de la búsqueda** abre el cuadro de diálogo, mostrar todas las entradas posibles del componente subyacente. Si recupera más de 300 entradas, aparece un mensaje.  
  
         a. En el panel izquierdo de la **resultados de la búsqueda** cuadro de diálogo, seleccione un campo.  
  
         b. Para mostrar los datos relevantes para ese campo concreto, haga clic en **obtener seleccionado**.  
  
         Aparecerá la pantalla siguiente.  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         Si la configuración de seguridad lo permite, puede cambiar los valores de los campos individuales.  
  
         Se abrirá el cuadro de diálogo siguiente:  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   Para comprobar la interfaz de componente con el método `Get`:  
  
         a. Especifique las claves existentes.  
  
         b. Haga clic en **obtener las propiedades existentes**.  
  
         De esta manera, recibirá las propiedades expuestas de la clave especificada.  
  
         Puede cambiar los valores si **actualizar el acceso** se ha especificado.  
  
         También puede comprobar la interfaz con el método `Create`.  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   Para comprobar la interfaz de componente con el método `Create`:  
  
         a. Escriba todos los valores de las claves.  
  
         b. Haga clic en **crear nuevos**.  
  
         Al escribir valores válidos en **crear claves**, se abre un panel que muestra los datos de JOBCODE después de expandirse el nombre de tabla con datos predeterminados en su lugar.  
  
         Ya puede cambiar los campos.  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         Los cambios se validan comparándolos con la lógica empresarial subyacente.  
  
3.  Para guardar los cambios, haga clic en el **guardar** icono.  
  
     Las claves que se han utilizado para crear el registro pueden usarse con el método Get para ver los datos. Los datos agregados pueden verse en el componente de PeopleSoft, tal y como se muestra en el ejemplo siguiente.  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     **Fecha de vigencia** es uno de los valores predeterminados.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)   
 [Apéndice C: usar Interfaces de componentes](../core/appendix-c-using-component-interfaces.md)