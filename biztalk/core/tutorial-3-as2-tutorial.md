---
title: 'Tutorial 3: Tutorial de AS2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629d1390b6471fb85a0b9e6fb6b605bedb043a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013469"
---
# <a name="tutorial-3-as2-tutorial"></a>Tutorial 3: Tutorial de AS2
En este tutorial, establezca una solución que reciba y envíe mensajes de cifrado EDIINT/AS2 a través de un transporte HTTP.  
  
 **Cómo funciona la solución del Tutorial**  
  
 La solución hará lo siguiente:  
  
- Recibir un mensaje AS2 de un socio comercial (Fabrikam)  
  
- Devolver una respuesta MDN de forma asíncrona al socio comercial  
  
- Procesar la carga EDI del mensaje AS2  
  
- Devolver una confirmación 997 al socio comercial (Fabrikam) a través de AS2  
  
- Enrutar un archivo XML que contenga la carga del mensaje EDI a una aplicación de servidor de la organización propia (Contoso).  
  
  > [!NOTE]
  >  Esta solución no utiliza la firma o cifrado para ayudar a garantizar la seguridad de los mensajes AS2.  
  
  **Componentes de tutorial**  
  
  Esta solución utilizará lo siguiente:  
  
- Un Http recibe filtro ISAPI de BTS para recibir el mensaje AS2/EDI del remitente **(/Contoso/BTSHTTPReceive.dll**).  
  
- Una página Web de ASPX para simular el socio comercial al devolver una confirmación 997 y MDN (**http://localhost/Fabrikam/Default.aspx**).  
  
- Un archivo de proyecto que va a utilizar para implementar un esquema 864 y otros esquemas (**Schemas.btproj**).  
  
- Una recepción HTTP unidireccional ubicación para recibir el archivo EDI (**Receive_AS2**). Esta ubicación de recepción utiliza la canalización AS2EdiReceive que contenga el descodificador AS2 y desensamblador EDI.  
  
- Un HTTP dinámico puerto de envío para devolver un MDN asíncrono (**Send_Async_MDN**). Este puerto de envío utiliza la canalización AS2Send que contenga el codificador AS2.  
  
- Un archivo unidireccional estático puerto de envío para enrutar la carga EDI en un archivo XML en una carpeta de back-end (**Send_Payload_EdiXml**). Este puerto de envío utiliza la canalización de envío PassThruTransmit.  
  
- Un HTTP unidireccional estático puerto de envío para devolver una confirmación 997 al socio comercial a través de AS2 (**Send_Async_997**). Este puerto de envío utiliza la canalización AS2Send que incluye el codificador AS2 pero no necesita el ensamblador EDI.  
  
- Un archivo de proyecto que va a utilizar para crear una aplicación para enviar el archivo EDI del socio comercial Fabrikam a BizTalk (**Sender.csproj**).  
  
  **Flujo de mensajes**  
  
  El flujo de mensajes en la solución completa será como se muestra en la siguiente figura:  
  
  ![Flujo de mensajes del tutorial de AS2](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")  
  
  Los componentes de tutorial procesan los mensajes como se muestra a continuación:  
  
1. Usa el **aplicación sender.exe** para enviar el mensaje EDI/AS2 original del socio comercial Fabrikam al equipo de BizTalk Server. Sender.exe envía el mensaje EDI/AS2 al directorio virtual de Contoso.  
  
   > [!NOTE]
   >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
   >   
   >  El mensaje de prueba es X12_00401_864.edi en \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial.  
  
2. El **Receive_AS2** unidireccional recibe ubicación recibe el mensaje EDI de Fabrikam. utiliza la extensión ISAPI BTSHTTPReceive.dll para recoger el archivo del directorio virtual de Contoso. La canalización de recepción descodifica el mensaje AS2, desensambla el intercambio EDI y, a continuación, coloca el mensaje XML en el cuadro de mensajes.  
  
3. La canalización de recepción genera un MDN para el mensaje AS2 y cuando se configura para que el MDN sea asíncrono, la canalización de recepción coloca el MDN en el cuadro de mensajes.  
  
4. La canalización de recepción genera una confirmación 997 en respuesta al intercambio EDI y coloca esta confirmación en el cuadro de mensajes.  
  
5. El **Send_Payload_EdiXml** puerto de envío unidireccional estático recoge la carga EDI del cuadro de mensajes, filtrando el BTS. Propiedad de contexto de MessageType.  
  
6. La carga del puerto de envío envía el archivo XML que contiene la carga EDI a la aplicación de Contoso de back-end, representada por el \\_EDIXMLToContoso carpeta. Este puerto de envío utiliza una canalización de envío PassThruTransmit.  
  
7. El **Send_Async_MDN** puerto de envío dinámico recoge el MDN asíncrono del cuadro de mensajes, filtrando por la propiedad de contexto EdiIntAS.IsAS2AsynchronousMdn.  
  
8. El MDN enviar puerto devuelve el MDN a la \\carpeta _MDNToFabrikam. Puesto que se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Option en el encabezado del mensaje (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) para enrutar el mensaje a la \\carpeta _MDNToFabrikam.  
  
9. El **Send_Async_997** enviar puerto recoge el 997 del cuadro de mensajes, filtrando el BTS. Propiedad de contexto de MessageType.  
  
10. El 997 puerto de envío utilizará transporte HTTP para enviar el mensaje 997 generada por el EdiReceive canalización de recepción la \\carpeta _997ToFabrikam. El puerto de envío envía el mensaje a la página default.aspx de Fabrikam, usando el URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**. La página default.aspx, envía el 997 a la \\carpeta _997ToFabrikam.  
  
    Para hacer este tutorial, debe tener conocimientos acerca de lo siguiente:  
  
-   Componentes de canalizaciones y canalizaciones de BizTalk Server  
  
-   Adaptador de HTTP  
  
-   Puertos y ubicaciones de recepción  
  
-   Los puertos de envío  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Preparar el tutorial de AS2](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [Paso 2: Crear e implementar el esquema X12 de ejemplo](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [Paso 3: Configurar un perfil de entidad y negocio para la organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [Paso 4: Configurar un perfil de entidad y negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [Paso 5: Configurar las páginas web de los socios comerciales](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [Paso 6: Configurar la ubicación de recepción EDI/AS2](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [Paso 7: Configurar el puerto de envío MDN](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [Paso 8: Configurar el puerto de envío 997](../core/step-8-configure-the-997-send-port.md)  
  
-   [Paso 9: Configurar el puerto de envío de carga EDI](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [Paso 10: Configurar el acuerdo entre socios comerciales X12 y AS2](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [Paso 11: Probar la solución AS2](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales de BizTalk Server](../core/biztalk-server-tutorials.md)