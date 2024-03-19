# [Microsoft Azure - Descrever a Arquitetura do Azure](https://learn.microsoft.com/pt-br/training/modules/describe-core-architectural-components-of-azure/5-describe-azure-physical-infrastructure)

### **O que é o Microsoft Azure**

O Azure é um conjunto de serviços de nuvem, em constante expansão, que ajuda você a superar os desafios empresariais atuais e se preparar para os desafios futuros. O Azure oferece a liberdade de criar, gerenciar e implantar aplicativos em uma enorme rede global usando suas ferramentas e estruturas favoritas.

### **O que o Azure oferece?**

<b>Inovação ilimitada.</b> Crie aplicativos e soluções inteligentes com tecnologia, ferramentas e serviços avançados para levar sua empresa para o próximo nível. Unifique perfeitamente sua tecnologia para simplificar o gerenciamento de plataformas e fornecer inovações de forma eficiente e segura em uma nuvem confiável.

<ul>
  <li><b>Traga vida às ideias:</b> Crie uma plataforma confiável para acelerar sua organização com serviços de IA e nuvem líderes do setor.</li>
  <li><b>Unifique perfeitamente</b> Gerencie com eficiência toda a infraestrutura, dados, análises e soluções de IA em uma plataforma integrada.</li>
  <li><b>Inove na confiança:</b> Conte com a tecnologia confiável de um parceiro dedicado à segurança e à responsabilidade.</li>
</ul>

### **O que posso fazer com o Azure?**

O Azure fornece mais de 100 serviços que permitem que você faça de tudo – desde a execução de aplicativos existentes em máquinas virtuais até a exploração de novos paradigmas de software, como bots inteligentes e realidade misturada.

Muitas equipes começam a explorar a nuvem migrando os aplicativos para VMs (máquinas virtuais) que são executadas no Azure. Migrar os aplicativos existentes para VMs é um bom começo, mas a nuvem é muito mais do que apenas um local diferente para executar suas VMs.

Por exemplo, o Azure fornece serviços de IA (inteligência artificial) e de ML (machine learning) que se comunicam naturalmente com os usuários por meio de recursos visuais, auditivos e de fala. Ele também fornece soluções de armazenamento que são ampliadas dinamicamente para acomodar grandes volumes de dados. Os serviços do Azure habilitam soluções que não seriam possíveis sem os recursos da nuvem.

## **Descrever a infraestrutura física do Azure**

<h2>Infraestrutura física</h2>

A infraestrutura física do Azure começa com datacenters. Conceitualmente, os datacenters são iguais aos grandes datacenters corporativos. São instalações com recursos organizados em racks com energia, refrigeração e infraestrutura de rede dedicadas.

Como um provedor de nuvem global, o Azure tem datacenters em todo o mundo. No entanto, esses datacenters individuais não estão diretamente acessíveis. Os datacenters são agrupados em Regiões do Azure ou em Zonas de Disponibilidade do Azure projetadas para ajudá-lo a obter resiliência e confiabilidade para suas cargas de trabalho críticas para os negócios.

<h2>Regiões</h2>

Uma região é uma área geográfica do planeta que contém pelo menos um data center, mas possivelmente vários, nas proximidades e conectado a uma rede de baixa latência. O Azure atribui e controla os recursos de modo inteligente dentro de cada região para garantir que as cargas de trabalho sejam balanceadas corretamente.

Quando você implanta um recurso no Azure, geralmente precisa escolher a região em que deseja que ele seja implantado.

<h2>Zonas de Disponibilidade</h2>

Zonas de disponibilidade são datacenters separados fisicamente dentro de uma região do Azure. Cada zona de disponibilidade é composta de um ou mais datacenters equipados com energia, resfriamento e rede independentes. Uma zona de disponibilidade é configurada para ser um limite de isolamento. Se uma zona ficar inativa, as outras continuarão funcionando. Zonas de disponibilidade são conectadas por meio de redes de fibra óptica privadas de alta velocidade.

<h2>Usar zonas de disponibilidade em seus aplicativos</h2>

É importante verificar se seus serviços e dados são redundantes para que você possa proteger suas informações em caso de falha. Ao hospedar sua infraestrutura, a configuração de sua redundância exigirá a criação de ambientes de hardware duplicados. O Azure pode ajudar a tornar seu aplicativo altamente disponível por meio das zonas de disponibilidade.

Você pode usar as zonas de disponibilidade para executar aplicativos críticos e incorporar alta disponibilidade à arquitetura do aplicativo, colocalizando seus recursos de computação, armazenamento, rede e dados em uma zona de disponibilidade e replicando em outras zonas de disponibilidade. Tenha em mente que pode haver um custo para duplicar seus serviços e transferir dados entre zonas de disponibilidade.

As zonas de disponibilidade são destinadas, principalmente, a VMs, discos gerenciados, balanceadores de carga e bancos de dados SQL.

Os serviços do Azure que dão suporte às zonas de disponibilidade enquadram-se em três categorias:

<ul>
  <li> Serviços em zonas: você fixa o recurso a uma zona específica (por exemplo, VMs, discos gerenciados, endereços IP).</li>
  <li> Serviços com redundância de zona: a plataforma replica automaticamente entre zonas (por exemplo, armazenamento com redundância de zona, Banco de Dados SQL).</li>
  <li> Serviços não regionais: os serviços estão sempre disponíveis em geografias do Azure e são resilientes a interrupções em toda a zona, bem como a interrupções em toda a região.</li>
</ul>

Mesmo com a resiliência adicional que as zonas de disponibilidade proporcionam, é possível que um evento possa ser tão grande que afete várias zonas de disponibilidade em uma só região. Para fornecer ainda mais resiliência, o Azure tem Pares de Regiões.

<h2>Pares de regiões</h2>

A maioria das regiões do Azure é emparelhada a outra região na mesma geografia (como EUA, Europa ou Ásia) a pelo menos 300 milhas (cerca de 480 km) de distância. Essa abordagem permite a replicação de recursos em uma geografia, o que ajuda a reduzir a probabilidade de interrupções devido a eventos como desastres naturais, conflitos civis, quedas de energia ou interrupções de rede física afetarem toda uma região. Por exemplo, se uma região em um par de regiões fosse afetada por um desastre natural, os serviços fariam failover automaticamente para a outra região nesse par.

Exemplos de pares de regiões no Azure são Oeste dos EUA emparelhado com Leste dos EUA e Sudeste da Ásia emparelhado com Leste da Ásia. Como o par de regiões está diretamente conectado e suficientemente afastado para ser isolado contra desastres regionais, você pode usá-lo para fornecer redundância de dados e serviços confiáveis.

<h2>Vantagens adicionais dos pares de regiões:</h2>

<ul>
  <li> Se ocorrer uma interrupção ampla do Azure, uma região de cada par será priorizada para que pelo menos uma seja restaurada quanto antes para os aplicativos hospedados nesse par de regiões.</li>
  <li> As atualizações planejadas do Azure são distribuídas para regiões emparelhadas uma por vez, de modo a minimizar o tempo de inatividade e o risco de interrupção dos aplicativos.</li>
  <li> Os dados continuam residindo na mesma geografia que seu par (com exceção do Sul do Brasil) para fins de jurisdição do imposto e aplicação da lei.</li>
</ul>

<h2>Regiões soberanas</h2>

Além das regiões normais, o Azure também tem regiões soberanas. Regiões soberanas são instâncias do Azure isoladas da instância principal do Azure. Talvez seja necessário usar uma região soberana para fins legais ou de conformidade.

As regiões soberanas do Azure incluem:

<ul>
  <li> SUS DoD Central, US Gov – Virgínia, US Gov Iowa, entre outros: essas regiões são instâncias lógicas e físicas do Azure isoladas da rede, destinadas a parceiros e órgãos do governo dos EUA. Esses datacenters são operados por cidadãos selecionados dos EUA e incluem certificações de conformidade adicionais.</li>
  <li> Leste da China, Norte da China, entre outros: essas regiões estão disponíveis por meio de uma parceria exclusiva entre a Microsoft e a 21Vianet, segundo a qual a Microsoft não mantém diretamente os data centers.</li>
</ul>

<h3>Para saber mais e aprender sobre a Computação em Nuvem da Microsoft, acesse os links abaixo:</h3>
            <ul>
                <li><a href="Microsoft Learn">https://learn.microsoft.com/pt-br/</a></li>
                <li><a href="Microsoft Azure">https://portal.azure.com/#home</a></li>
                <li><a href="Arquitetura do Azure">https://learn.microsoft.com/pt-br/training/modules/describe-core-architectural-components-of-azure/2-what-microsoft-azure</a></li>
            </ul>

