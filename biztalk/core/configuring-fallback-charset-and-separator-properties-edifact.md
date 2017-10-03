---
title: Configurar las propiedades de separador (EDIFACT) y el juego de caracteres de reserva | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b517a98130f2d245d68083dc16c65865950800c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a>Configuración de propiedades de juegos de caracteres y separadores de reserva (EDIFACT)
En el acuerdo de reserva, puede especificar el juego de caracteres (UNA) que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para validar las propiedades de entidades al crear el sobre para un mensaje EDIFACT saliente. También puede especificar los separadores y terminadores (UNB) que se usarán para los segmentos en el intercambio.  
  
 En el segmento UNZ, se define cómo BizTalk Server genera un segmento UNA para un intercambio codificado en EDIFACT que envía a la entidad. El segmento UNA define los caracteres que se usarán como separadores e indicadores para un intercambio con codificación EDIFACT. Use este segmento sólo si el intercambio contiene caracteres separadores no estándar.  
  
 En el segmento UNB, se define el juego de caracteres EIFACT que se va a usar.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-character-set-and-separators"></a>Para configurar el juego de caracteres y los separadores  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2.  En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en **Charset y Separadores**.  
  
3.  En el **sintaxis (UNB1)** sección, realice lo siguiente:  
  
    1.  Para **identificador (UNB1.1)**, escriba el carácter EDIFACT establecido se aplicará al intercambio de salida. Este campo es obligatorio.  
  
    2.  Para **versión (UNB1.2)**, seleccione un valor entre **1** y **4**. Se trata de un campo opcional.  
  
4.  En el **separadores** sección, realice lo siguiente:  
  
    1.  Para **separador de elementos de datos de componente (UNA1)**, escriba un valor para el separador de elementos de datos de componente que separa los elementos de datos simples dentro de los elementos de datos compuestos. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambia automáticamente si modifica su formato.  
  
    2.  Para **separador de elementos de datos (UNA2)**, escriba un valor para el separador de elementos de datos que separa los elementos de datos compuestos que consten de dos o más elementos de datos simples o elementos de datos simples que no forman parte de un compuesto. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambia automáticamente si modifica su formato.  
  
    3.  Para **notación Decimal (UNA3)**, seleccione la notación decimal que se usará en el intercambio saliente.  
  
    4.  Para **indicador de versión (UNA4)**, escriba un valor para el indicador de versión que indica que el carácter siguiente no es un separador de sintaxis, terminador o carácter de versión, pero forma parte de los datos originales. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambia automáticamente si modifica su formato.  
  
    5.  Para **separador de repeticiones (UNA5)**, escriba un valor para el separador de repeticiones que se usa para separar segmentos que se repiten en un conjunto de transacciones. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambia automáticamente si modifica su formato.  
  
    6.  Para **terminador de segmento (UNA6)**, escriba un valor para el terminador de segmento que indica el final de un segmento EDI.  
  
    7.  Para **sufijo UNA6**, seleccione el carácter que BizTalk Server utilizará con el identificador de segmento, puede ser **ninguno**, **CR** (retorno de carro), **LF** (avance de línea) o **CR LF** (retorno de carro/línea fuente). Si designa un sufijo, el elemento de datos de terminador de segmentos puede estar vacío. Si el terminador de segmentos se deja vacío, debe designar un sufijo. La combinación de terminador de segmento y sufijo puede ser cualquiera de las siguientes:  
  
        -   Terminador de segmento  
  
        -   Terminador de segmento + retorno de carro  
  
        -   Terminador de segmento + retorno de carro/avance de línea  
  
        -   Retorno de carro  
  
        -   Avance de línea  
  
        -   Retorno de carro/avance de línea  
  
5.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar y aceptar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)