---
title: 'Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de respuesta de la consulta de disponibilidad mediante el Explorador de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a>Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de la consulta/respuesta de disponibilidad
En este paso, creará puertos de envío mediante el adaptador de SQL proporcionado por el servidor BizTalk Server. Usará el puerto SQL para enviar la respuesta de precio y disponibilidad 3A2 al sistema ERP de Contoso y recibirla de él.  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a>Para configurar el puerto de envío mediante el adaptador de SQL  
  
1.  En Visual Studio, en el **vista** menú, haga clic en **el Explorador de BizTalk**.  
  
2.  En el Explorador de BizTalk, haga clic con el botón secundario en **Puertos de envío**y en **Agregar puerto de envío**.  
  
3.  En el cuadro de diálogo Crear nuevo puerto de envío, seleccione **Puerto de petición-respuesta estático** en la lista desplegable y haga clic en **Aceptar**.  
  
4.  En el cuadro de diálogo Propiedades del puerto de envío de petición-respuesta estático, en el cuadro **Nombre** , escriba **3A2SQLReqResponseSendPort**.  
  
5.  En la ventana Propiedades en el encabezado **General** , seleccione **SQL** como el **Tipo de transporte**.  
  
6.  En el cuadro **Dirección URI** , haga clic en el botón de puntos suspensivos (**…**).  
  
7.  En el cuadro de diálogo Propiedades de transporte SQL, haga clic en el botón de puntos suspensivos (**…**) que se encuentra junto al cuadro **Cadena de conexión** .  
  
8.  En el cuadro de diálogo Propiedades de vínculo de datos, en el cuadro **Seleccione o escriba un nombre de servidor** , escriba **localhost**.  
  
9. Seleccionar **Usar seguridad integrada de Windows**.  
  
10. En el cuadro **Seleccione la base de datos del servidor** , seleccione **Contoso**y, a continuación, haga clic en **Aceptar**.  
  
11. En el cuadro de diálogo Propiedades de transporte SQL, en el cuadro **Target Namespace de documento** , escriba **http://Contoso.com/Price**.  
  
12. En el cuadro **Nombre de elemento raíz de documento de respuesta** , escriba **rootPriceResponse**y, a continuación, haga clic en **Aceptar**.  
  
13. En el panel de la izquierda del cuadro de diálogo Propiedades del puerto de envío de petición-respuesta estático, haga clic en **Enviar**.  
  
14. En el cuadro de diálogo estático petición-respuesta enviar puerto propiedades-configuraciones-enviar-General, en la **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
15. En el cuadro **Canalización de recepción** , seleccione **Microsoft.BizTalk.DefaultPipelines.XMLReceive**y, a continuación, haga clic en **Aceptar**.  
  
16. En el Explorador de BizTalk, haga clic con el botón derecho en **3A2SQLReqResponseSendPort**, y después clic en **Dar de alta**. Haga clic en nuevo con el botón derecho y haga clic en **Iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y modificar el proceso privado de Contoso](creating-and-modifying-the-private-process-for-contoso.md)