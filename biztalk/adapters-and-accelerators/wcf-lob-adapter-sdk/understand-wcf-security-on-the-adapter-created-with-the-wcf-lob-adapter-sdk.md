---
title: Comprender la seguridad WCF en el adaptador creado con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf0c62c3d0c37c1f69cb944112ff832dade5ec4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22224012"
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a>Comprender la seguridad WCF en el adaptador creado con el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] amplía la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal y se basa en la infraestructura de mensajería y la API que proporciona.  Un adaptador de LOB de WCF es necesario establecer una conexión con sistemas de destino y, por lo tanto, es necesario configurar el adaptador con autenticación y otra información de seguridad necesarios para realizar las conexiones del sistema de destino.  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] es una plataforma de programación distribuida basada en mensajes SOAP que pueden transmitirse a través de muchos nodos diferentes, SOAP intermediarios, los servidores de seguridad y potencialmente el Internet en la ruta del sistema de línea de negocio para el adaptador y en el cliente. Esto podría suponer un número de amenazas de seguridad diferente para el adaptador y el escenario de implementación.  
  
 Seguridad juega un papel importante en cualquier solución de arquitectura empresarial. Puede aprovechar la confidencialidad, integridad, autenticación y características de autorización proporcionados en el modelo de seguridad WCF para ayudar a proteger el adaptador frente a amenazas de seguridad. También debe tener en cuenta el transporte y seguridad de nivel de mensaje entre el adaptador y el sistema de destino para proteger la comunicación entre estas dos entidades. Aunque WCF proporciona un amplio conjunto de WS-* especificaciones, implementación de estas funciones de seguridad avanzada estándares en el adaptador dependerá de las capacidades proporcionadas por el sistema de línea de negocio.  
  
 Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] seguridad incluida una información general, conceptos, escenarios comunes y los procedimientos recomendados, consulte [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)