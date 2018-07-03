---
title: 'Paso 3: Modificar el proceso de interfaz de socio | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b5b6d2f6b0fcbf13ab521bc318eda54ece55f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003613"
---
# <a name="step-3-edit-the-partner-interface-process"></a>Paso 3: Modificar el proceso de interfaz de socio
En este paso, edite los valores de configuración de proceso de interfaz de socio (PIP) para deshabilitar el transporte seguro si no tiene un certificado de capa de Sockets seguros (SSL) configurado en Microsoft® Internet Information Services (IIS). Dado que el escenario de bucle invertido no es compatible con la firma de mensajes entrantes y salientes, debe cambiar la configuración predeterminada para continuar con el tutorial. Modifique el PIP STD_0C1_R01.02.  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>Para editar el PIP STD_0C1_R01.02  
  
1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda **BizTalk \<versión\> Acelerador para RosettaNet**, haga clic en **configuración del proceso** , haga clic en **STD_0C1_R01.02**y, a continuación, haga clic en **propiedades**.  
  
2. En el cuadro de diálogo STD_0C1_R01.02Properties, en el **actividad** pestaña, establezca el **se requiere de transporte seguro** opción `False`. Realice este paso únicamente si no tiene un certificado SSL en el servidor Web de IIS.  
  
3. Establecer el **sin repudio necesario** a `False`, establezca **se necesita autorización** a `False`, establezca **sin repudio del origen y del contenido** a `False`y, a continuación, haga clic en **Aceptar**.  
  
    Esto deshabilita el uso de certificados para firmar mensajes y de no repudio.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Crear un acuerdo comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [Propiedades de autorización y no rechazo](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)