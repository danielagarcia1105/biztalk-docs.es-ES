---
title: Componente de canalización del Inspector de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, custom pipelines
- pipelines, Message Inspector Pipeline Component
- Message Inspector Pipeline Component
- pipelines, creating
ms.assetid: d9c00718-c8cd-4289-8f58-e4edc61b9a05
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6b8a2d9bcd503b1b295110665827ead3e85ee6
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855623"
---
# <a name="message-inspector-pipeline-component"></a>Componente de canalización del inspector de mensajes
Este componente de canalización le permite examinar todas las partes de un mensaje de varias partes y el contexto del mensaje para determinar si hay un problema con el mensaje. Este componente se usa para solucionar problemas.  
  
 El componente de canalización coloca los archivos XML en el directorio que usted designe. Cada uno de estos archivos contiene una de las cuatro partes de un mensaje de RNIFv2.0 (encabezado de preámbulo, encabezado de entrega, encabezado de servicio y contenido de servicio) o las tres partes de un mensaje de RNIFv1.1 (encabezado de preámbulo, encabezado de servicio y contenido de servicio). Otro archivo XML contiene el contexto del mensaje.  
  
 Debe generar este componente en una canalización personalizada y adjuntarlo a un puerto de envío. Cree un filtro en el puerto de envío para suscribirse a los mensajes que desea supervisar. Esta solución de problemas se produce en adición al procesamiento estándar que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ya lleva a cabo.  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a>Generación de una canalización personalizada mediante el componente de canalización del inspector de mensajes  
 Para usar el componente de canalización del inspector de mensajes, debe generar e implementar una canalización personalizada que incluya el componente. Para obtener más información, vea "Crear canalizaciones con Diseñador de canalizaciones" en la Ayuda de BizTalk Server.  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a>Para implementar el componente de canalización del inspector de mensajes  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
3.  Mover a C:\Program Files (x86) \Microsoft BizTalk \<versión\> seleccione Acelerador para el componente de canalización del Inspector de RosettaNet\SDK\Message **MessageInspector.csproj**y, a continuación, haga clic en  **Abra**.  
  
4.  Abra el símbolo del sistema de Visual Studio.  
  
5.  En el símbolo del sistema, vaya a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Inspector canalización Component\obj\debug.  
  
6.  En el símbolo del sistema, escriba **"sn -k MessageInspector.snk"** para crear una clave y, a continuación, presione ENTRAR.  
  
7.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **MessageInspector**y, a continuación, haga clic en **propiedades**.  
  
8.  En la página **Propiedad de MessageInspector**  , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** .  
  
9. En **elegir un archivo de clave de nombre seguro** lista desplegable, vaya a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Inspector canalización Component\obj\debug y seleccione **MessageInspector.snk** y, a continuación, haga clic en **abiertos**.  
  
10. En el Explorador de soluciones, haga clic con el botón derecho en **MessageInspector**y, a continuación, haga clic en **Generar**. En el panel de salida, compruebe que la compilación se realizó correctamente.  
  
11. Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
12. En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Inspector canalización Component\obj\debug, haga clic en  **Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**y, a continuación, haga clic en **copia**.  
  
13. Mover a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para los componentes de RosettaNet\Pipeline, haga clic en **componentes de canalización**y, a continuación, haga clic en **pegar**.  
  
14. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
15. En el cuadro de diálogo **Nuevo proyecto** , en el panel Plantillas, seleccione **Proyecto vacío de servidor BizTalk Server**y, en el cuadro **Nombre** , escriba un nombre para el proyecto. En el cuadro **Ubicación** , vaya a la carpeta en la que desea guardar el proyecto y, a continuación, haga clic en **Aceptar**.  
  
16. En el Explorador de soluciones, haga clic con el botón derecho en el nombre del proyecto, seleccione **Agregar**y luego haga clic en **Agregar nuevo elemento**.  
  
17. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Canalización de envío**y, en el cuadro **Nombre** , escriba un nombre para el archivo de canalización personalizada y, a continuación, haga clic en **Abrir**.  
  
    > [!NOTE]
    >  Agregue el componente de canalización del inspector de mensajes solo para puertos de envío, no para puertos de recepción.  
  
18. Haga clic con el botón derecho en el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas y, a continuación, haga clic en **Agregar o quitar elementos**.  
  
19. En el cuadro de diálogo **Personalizar cuadro de herramientas** , en la pestaña **Componentes de canalización de BizTalk** , seleccione **Componente del inspector de mensajes de BTARN**y haga clic en **Aceptar**.  
  
20. En el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas, mantenga presionado **Componente del inspector de mensajes de BTARN**y arrastre el componente al cuadro **Colocar aquí** .  
  
21. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en el nombre del proyecto de canalización y, a continuación, haga clic en **propiedades**.  
  
22. En el cuadro de diálogo **Páginas de propiedades** , haga clic en **Propiedades comunes**y, a continuación, haga clic en **Ensamblado**.  
  
23. En el panel derecho, en el cuadro de texto asociado con **archivo de clave de ensamblado**, haga clic en el botón de puntos suspensivos, lleve a C:\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Message Inspector Canalización Component\obj\debug, seleccione **MessageInspector.snk**y, a continuación, haga clic en **Aceptar**.  
  
24. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Diseñador de canalizaciones, seleccione la **componente de Inspector de mensajes de BTARN** forma.  
  
25. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ventana Propiedades, en la **directorio** , escriba el nombre del directorio al que va a colocar los archivos XML.  
  
26. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**. Compruebe que la compilación se realiza correctamente.  
  
27. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**. Compruebe que la implementación se realiza correctamente.  
  
28. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **vista** menú, haga clic en **el Explorador de BizTalk**.  
  
29. Haga clic con el botón secundario en **Puertos de envío**y seleccione **Agregar puerto de envío**.  
  
30. En el cuadro de diálogo **Crear nuevo puerto de envío** , haga clic en **Aceptar**.  
  
31. En el cuadro de diálogo **Propiedades de puerto de envío** , en el cuadro **Nombre** , escriba un nombre para el puerto de envío; con **Principal** seleccionado en el panel izquierdo, haga clic en **Tipo de transporte** en el panel derecho, y seleccione **Archivo**.  
  
32. En el cuadro de diálogo **Propiedades de puerto de envío** , en el cuadro **Dirección (URI)** , haga clic en el botón de puntos suspensivos (**...**).  
  
33. En el cuadro de diálogo **Propiedades de transporte de archivo** , escriba el nombre de la carpeta de **destino** , haga clic en **Enviar** en el panel izquierdo y, a continuación, para la **Canalización de envío** en el panel derecho, seleccione la canalización personalizada que acaba de crear.  
  
34. Haga clic en **filtra & asigna** en el panel izquierdo y, a continuación, haga clic en **filtros**.  
  
35. Escriba una expresión de filtro en el panel derecho, que designe el tipo de archivos para los que la canalización debe colocar archivos XML. Por ejemplo, si desea colocar archivos para todos los mensajes de RNIF v1.1, para **Propiedad** seleccione Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction y, para **Operador** , seleccione "Existe" y, a continuación, haga clic en **Aceptar**.  
  
36. En el Explorador de BizTalk, haga clic en el puerto de envío que acaba de crear, haga clic en **Dar de alta**, haga clic con el botón derecho en el puerto de envío de nuevo y, a continuación, haga clic en **Iniciar**.  
  
## <a name="remarks"></a>Notas  
 En el procesamiento normal, solo puede examinar una de las partes del mensaje cada vez (la parte que ha designado como el cuerpo del mensaje en la orquestación). Por lo tanto, solo puede examinar una de las partes en la consola de administración de BizTalk y su capacidad para solucionar problemas es limitada. El componente de canalización del inspector de mensajes le ayuda a superar esta limitación.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
