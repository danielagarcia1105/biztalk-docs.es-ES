---
title: Personalizar un proceso privado para trabajar con un PIP específico | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77abdf870f0813bb5b9e1dd7a039b99ef0726c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001509"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a>Personalizar un proceso privado para trabajar con un PIP específico
Puede crear una expresión de filtro que hará que a un contestador de orquestación de procesos de privados para procesar o no las instancias de proceso de un proceso de interfaz de socio (PIP) específico. Esto ofrece la flexibilidad de crear un proceso privado personalizado para recibir y procesar algunas instancias PIP y el uso privado predeterminado procesos todas las demás instancias PIP.  
  
 Para crear un proceso privado personalizado para trabajar con un determinado PIP o múltiples PIP específico, cree una expresión de filtro para la forma recepción de la orquestación de procesos privado. Un ejemplo es la orquestación PIP3A4PrivateResponder.odx en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK. Se encuentra en \< *unidad*\>: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PIP3A4Process Rules\PIP3A4PrivateResponder de negocios utilizando.  
  
 Además de crear un proceso privado que procesan solo las instancias de un PIP específico, debe personalizar el proceso privado de BTARN predeterminado para que no procesará las instancias de ese PIP.  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a>Para personalizar un proceso privado del Respondedor para trabajar con un PIP específico  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], crear una orquestación de procesos de privados de servicio de respuesta personalizado para trabajar con un PIP específico. Puede basar la orquestación en la orquestación de proceso privado predeterminado Respondedor BTARN.  
  
   > [!NOTE]
   >  Puede encontrar el valor predeterminado orquestación del Respondedor del proceso de privado, denominado PrivateResponder.odx en el SDK de BTARN. Se encuentra en  *\<unidad\>*: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateResponder.  
  
2. Agregue la orquestación personalizada al proyecto de BizTalk. Asegúrese de que el proyecto tiene una referencia al archivo Microsoft.Solutions.BTARN.GlobalSchemas.dll.  
  
3. Abra la orquestación personalizada en el Diseñador de orquestaciones.  
  
4. Haga clic en la primera **recepción** forma que activa la orquestación y, a continuación, haga clic en **Editar expresión de filtro**.  
  
   > [!NOTE]
   >  La forma de recepción para la orquestación de proceso privado predeterminado Respondedor BTARN tiene dos condiciones de filtro: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" o Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction". Esta expresión se asegura de que la orquestación procesa los mensajes de RosettaNet. Conservar esta expresión de filtro en la orquestación personalizada.  
  
5. En el **expresión de filtro** cuadro de diálogo, en la columna de la propiedad en la primera fila abierta, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable, en la columna de operador Seleccione **==** en la lista desplegable, en la columna valor, escriba el código PIP de tres dígitos, por ejemplo, escriba **3A4**.  
  
6. Haga clic en **Aceptar**.  
  
7. Abra el proyecto de orquestación de procesos de privados del servicio de respuesta predeterminado (PrivateResponder.btproj) en el Diseñador de orquestaciones. Asegúrese de que el proyecto tiene una referencia de trabajo en el archivo Microsoft.Solutions.BTARN.GlobalSchemas.dll.  
  
8. Haga doble clic en **PrivateResponder.odx**.  
  
9. Haga clic en el **ReceiveFromPublicProcessResponder** forma recepción y, a continuación, haga clic en **Editar expresión de filtro**.  
  
10. En el **expresión de filtro** cuadro de diálogo, en la columna de la propiedad en la primera fila abierta, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable. En la columna de operador, seleccione **! =** en la lista desplegable. En la columna valor, escriba el código PIP de tres dígitos, por ejemplo, escriba "**3A4"**.  
  
11. Haga clic en **Aceptar**.  
  
12. En el Explorador de soluciones, haga clic en el proyecto que contiene la orquestación y, a continuación, haga clic en **compilar**.  
  
13. Una vez que se ha compilado correctamente el proyecto, haga clic en el proyecto y, a continuación, haga clic en **implementar**.  
  
14. En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
15. Mover a \< *unidad*\>: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateResponder, seleccione **PrivateResponder.odx**y, a continuación, haga clic en **Aceptar**.  
  
16. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y, después, haga clic en **Generar**.  
  
17. Una vez que se ha compilado correctamente el proyecto, haga clic en el proyecto y, a continuación, haga clic en **implementar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)