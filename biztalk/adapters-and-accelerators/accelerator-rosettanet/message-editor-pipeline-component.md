---
title: Componente de canalización del Editor de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f0ac419e64b8a1a949fb2e3044be9de670b387a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975429"
---
# <a name="message-editor-pipeline-component"></a>Componente de canalización del editor de mensajes
Este componente permite editar automáticamente cualquier parte de un mensaje de varias partes dentro de una canalización de envío o recepción. Este componente se agrega a una canalización existente para configurar el reemplazo como parte del procesamiento normal.  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a>Crear el componente de canalización del editor de mensajes en una canalización existente  
 Para usar el componente de canalización del editor de mensajes, debe agregar el componente a una canalización existente. Para obtener más información, consulte "Creación de canalizaciones con Diseñador de canalizaciones" en la Ayuda de BizTalk Server.  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a>Para agregar el componente de canalización del editor de mensajes en una canalización existente  
  
1. Inicie Visual Studio.  
  
2. En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
3. Mover a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, seleccione **MessageEditor.csproj**y, a continuación, haga clic en **abierto** .  
  
4. Inicie el símbolo del sistema de Visual Studio.  
  
5. En el símbolo del sistema, vaya a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.  
  
6. En el símbolo del sistema, escriba **sn -k MessageEditor.snk** para crear una clave y, a continuación, presione ENTRAR.  
  
7. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **MessageEditor**y, a continuación, haga clic en **propiedades**.  
  
8. En la página **Propiedad de MessageEditor** , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** .  
  
9. En **elegir un archivo de clave de nombre seguro** lista desplegable, vaya a C:\Program Files (x86) \Microsoft BizTalk \<versión\> aceleración de menú rosettanet\sdk\message Editor Pipeline Component\obj\debug y seleccione **MessageEditor.snk** y, a continuación, haga clic en **abierto**.  
  
10. En el Explorador de soluciones, haga clic con el botón derecho en **MessageEditor**y, a continuación, haga clic en **Compilar**. En el panel de salida, compruebe que la compilación se realizó correctamente.  
  
11. Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
12. En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] haga clic en el explorador, vaya a C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, y, a continuación, haga clic en **copia**.  
  
13. Vaya a C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, haga clic con el botón derecho en **Componentes de canalización**y haga clic en **Pegar**.  
  
14. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **abierto**y, a continuación, haga clic en **proyecto**.  
  
15. Abra el proyecto que contiene la canalización a la que desea agregar el editor.  
  
16. En el Explorador de soluciones, haga doble clic en el nombre de la canalización para abrir la canalización en el Diseñador de canalizaciones.  
  
17. Haga clic con el botón derecho en el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas y, a continuación, haga clic en **Agregar o quitar elementos**.  
  
18. En el cuadro de diálogo **Personalizar cuadro de herramientas** de la pestaña **Componentes de canalización de BizTalk** , seleccione **Componente del editor de mensajes de BTARN**y haga clic en **Aceptar**.  
  
19. En el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas, mantenga presionado **Componente del editor de mensajes de BTARN**y arrastre el componente a la posición que desee en la canalización.  
  
20. En el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas, mantenga presionado **Componente del editor de mensajes de BTARN**y arrastre el componente a la posición que desee en la canalización.  
  
    > [!NOTE]
    >  Se recomienda agregar el componente de canalización del editor de mensajes después de la fase de desensamblado del componente de canalización de recepción o en la fase de preensamblado del componente de canalización de envío.  
  
21. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Diseñador de canalizaciones, seleccione la **componente Editor de mensajes de BTARN** forma.  
  
22. En el panel de propiedades, en el cuadro de texto asociado a **Consulta XPath**, escriba el nombre del elemento XPath para el que desea cambiar el valor.  
  
23. En el cuadro de texto asociado a **Valor XPath**, escriba el valor en el que desea establecer el elemento XPath.  
  
24. En el Explorador de soluciones, haga clic con el botón derecho en el nombre del proyecto y, a continuación, haga clic en **Compilar**. Compruebe que la compilación se realiza correctamente.  
  
25. En el Explorador de soluciones, haga clic con el botón derecho en el nombre del proyecto y, a continuación, haga clic en **Implementar**. Compruebe que la implementación se realiza correctamente.  
  
## <a name="example"></a>Ejemplo  
 Para cambiar el valor del elemento `ProprietaryDocumentIdentifier` en el esquema de PIP 0C1, agregue la consulta XPath que se muestra en la sección de código siguiente a la propiedad de la consulta XPath del componente de canalización del editor de mensajes.  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 Para obtener una consulta XPath completa, abra el esquema en el Editor de BizTalk y, a continuación, copie Xpath de la propiedad `Instance XPath` que aparece en la ventana Propiedades. La consulta XPath que proporcione debe incluir todas las referencias de espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
