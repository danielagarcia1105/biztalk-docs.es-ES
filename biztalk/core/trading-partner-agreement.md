---
title: Acuerdo de socio comercial | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e40a3847-ee36-4a75-ab50-def9b0caf07e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a62ada3317bc347a6d39af9fb2f983e02647e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="trading-partner-agreement"></a>Acuerdo de socios comerciales
## <a name="overview"></a>Información general
Un acuerdo de socios comerciales (TPA) se define como un acuerdo vinculante y definitivo entre dos socios comerciales para la transacción de mensajes a través de un protocolo B2B específico. Los acuerdos unen propiedades comunes de procesamiento de mensaje bidireccionales de perfiles específicos del negocio de ambos socios. Es una recopilación completa de todos los aspectos que rigen una transacción empresarial entre dos socios comerciales. Un TPA normalmente deriva de los perfiles de cada socio comercial, con la capacidad de personalizar y sobrescribir la configuración necesaria.  
  
 Es decir, un TPA es un acuerdo entre dos perfiles de negocio para usar un protocolo de codificación de mensajes específico o un protocolo de transporte específico mientras intercambian mensajes B2B entre ellos.  
  
 ![Perfiles con acuerdos de socios comerciales](../core/media/tradingpartneragreement.gif "TradingPartnerAgreement")  
  
 En la ilustración anterior, hay un acuerdo entre los perfiles de "Envío" y "Factura" de Fabrikam y Contoso respectivamente, para uso el X12 codificación para los mensajes de negocio (**acuerdo de codificación**) y el transporte de AS2 para intercambio de mensajes (**acuerdo de transporte**). Puede haber varios acuerdos de este tipo entre varios perfiles de negocios. Por ejemplo, puede haber un acuerdo entre los perfiles "Pagos" y "Factura" para usar el estándar de codificación de mensajes EDIFACT. Todos estos acuerdos para todos los perfiles para un par de socios comerciales constituyen un **asociación** entre los dos socios comerciales.  
  
## <a name="bi-directional-agreements"></a>Acuerdos bidireccionales  
 Cada acuerdo entre dos perfiles de negocio es bidireccional. Por ejemplo, el acuerdo entre los perfiles de negocio "Envío" y "Factura" contendrá propiedades para procesar mensajes:  
  
-   Recibidos por el perfil "Envío" del perfil "Factura" y  
  
-   Enviados por el perfil "Envío" al perfil "Factura"  
  
 En términos más sencillos, un acuerdo bidireccional es una colección de dos acuerdos unidireccionales. Los acuerdos unidireccionales pueden considerarse una colección de propiedades que definen cómo se realiza una transacción de mensajes de la entidad A a la entidad B. El otro acuerdo unidireccional puede considerarse una colección de propiedades que definen cómo se realiza la transacción de mensajes de la entidad B a la entidad A.  
  
## <a name="considerations-when-defining-an-agreement"></a>Consideraciones al definir un acuerdo  
 Al crear un acuerdo de socios comerciales, deben tenerse en cuenta los siguientes puntos:  
  
-   Para dos perfiles de negocio que intercambian mensajes B2B entre ellos, es obligatorio definir un acuerdo de codificación de mensajes. Las divisiones pueden elegir tener un acuerdo AS2 únicamente si desean usar el protocolo AS2 para transferir mensajes. Por ejemplo, no se requiere un acuerdo AS2 si las divisiones de negocio eligen transferir los mensajes por correo electrónico.  
  
-   Si dos perfiles de negocio admiten la codificación X12 y EDIFACT, y ambos perfiles acuerdan usar ambos protocolos de codificación al intercambiar mensajes, deben crearse acuerdos independientes para cada protocolo. Debe haber un acuerdo para el protocolo X12 y un acuerdo para el protocolo EDIFACT. No puede haber un acuerdo único que pueda usarse para ambos protocolos.  
  
-   El acuerdo de codificación para mensajes X12 y EDIFACT y el acuerdo de transporte (para AS2) no pueden ser parte de un acuerdo. Deben crearse acuerdos independientes para ambos.  
  
## <a name="global-or-fallback-agreement"></a>Acuerdo de reserva o global  
 Algunas organizaciones de negocios pueden elegir tener un conjunto particular de mecanismos de procesamiento B2B sin diferenciar en los socios comerciales implicados en una mensajería B2B específica. En esencia, estas organizaciones de negocios tienen una sola configuración de protocolo B2B común, que se comparte con el resto de socios comerciales. Por lo tanto, puesto que estas organizaciones no necesitan tener configuraciones específicas para socios específicos, la configuración del protocolo B2B se define para el propio socio comercial y no para un perfil de negocios comercial. En [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], dichas organizaciones comerciales se reflejan como **socios comerciales globales**. Otras empresas que necesitan comerciar con un negocio representado como un socio comercial global usan acuerdos con el socio comercial global que se denominan **acuerdo de socios comerciales Global**. Estos acuerdos cumplen la configuración de protocolo y codificación de mensajes definida para el socio comercial global.  
  
 Esta configuración definida a nivel global también puede ser útil en escenarios donde la configuración de protocolo específica del perfil entre dos socios comerciales no formula un acuerdo de socios comerciales. En este escenario, la organización que hospeda [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] puede usar la configuración de protocolo definida para el socio para formular un acuerdo con otro perfil de negocios comercial. En tales casos, el Acuerdo llegaron al usar la configuración de protocolo global definida para el socio comercial se denomina la **acuerdo de socios comerciales de reserva**.  

## <a name="learn-next"></a>Obtenga información acerca de continuación

[Perspectiva general: definir un comerciales de solución de administración de socios comerciales](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md)