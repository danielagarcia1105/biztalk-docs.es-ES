---
title: Configurar las opciones de reserva de Host Local de reserva (configuración de conjunto de transacciones de X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb13da3e0bc9e0c3ee676a8bf01d484a4201a80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979029"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>Configuración de las opciones de host local de reserva (configuración del conjunto de transacciones de X12)
Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio. Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar. En esta página del contrato de reserva, especifique el espacio de nombres de destino de reserva. Cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
> [!NOTE]
>  Este tema se aplica también a valores de configuración relacionados con HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>Para configurar el host local para conjuntos de transacciones  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2. En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración del conjunto de transacciones** sección, haga clic en **configuración de Host Local** .  
  
3. Seleccione **convertir formato decimal implícito Nn a valor numérico 10 base** para convertir un número EDI especificado con el formato Nn en un valor numérico de base 10 en el XML intermedio en BizTalk Server.  
  
   > [!NOTE]
   >  Después de esta conversión, puede haber errores en la validación de la longitud del XML intermedio. Ello se debe a que el número en formato numérico de base 10 incluye un decimal, lo que conlleva que su longitud sea superior en uno al número en formato Nn. Para resolver este problema, puede agregar un valor de **1** en el valor de longitud mínima o máxima.  
  
4. Seleccione **crear etiquetas XML vacías para separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.  
  
5. Para **Target Namespace**, escriba (o seleccione en la lista desplegable) el espacio de nombres de destino que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se utiliza para determinar el esquema para procesar el mensaje recibido.  
  
6. Haga clic en **aplicar** para aceptar los cambios o haga clic en **Aceptar** para introducir y validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de X12 para valores de conjuntos de transacciones](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)