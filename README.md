# Diagrama de Atividades - Viva Saúde Recife

```mermaid
flowchart TD
    A[Início] --> B{Opções de Busca}
    
    %% História 1 & 7 - Posto mais próximo + Mapa
    B --> C1["📍 Posto Mais Próximo (Hist. 1 & 7)"]
    C1 --> D1{Usar geolocalização?}
    D1 -->|Sim| E1[📱 Solicitar permissão GPS]
    D1 -->|Não| F1[🏠 Digitar endereço]
    E1 --> G1[🛰️ Detectar localização]
    G1 --> H1[🔍 Buscar postos próximos]
    F1 --> H1
    H1 --> I1["📋 Lista + 🗺️ Mapa interativo"]
    
    %% História 2, 6, 8, 9 - Visualização por região
    B --> C2["🏙️ Buscar por Região (Hist. 2,6,8,9)"]
    C2 --> D2["Escolha:
    - Distrito (Hist.8)
    - Bairro (Hist.9)
    - Cidade (Hist.6)"]
    D2 --> E2[🌐 Carregar postos]
    E2 --> F2[📊 Exibir cards com foto, endereço]
    
    %% História 3, 5, 10 - Informações detalhadas
    F2 --> G2["ℹ️ Detalhes do Posto (Hist.3,5,10)"]
    G2 --> H2["- Horários (Hist.10)
    - Especialidades (Hist.5)
    - Estrutura
    - Telefone"]
    
    %% História 4 - Busca por especialidade
    B --> C3["🩺 Busca por Especialidade (Hist.4)"]
    C3 --> D3[🔎 Campo de busca]
    D3 --> E3[🏷️ Filtros: distrito/bairro]
    E3 --> F3[📅 Horários disponíveis]
    
    %% História 11 - Conteúdo educativo
    B --> C4["📚 Saúde Preventiva (Hist.11)"]
    C4 --> D4["Categorias:
    - Vacinação
    - Doenças crônicas
    - Primeiros socorros"]
    
    %% História 12 - Descrição de distritos
    F2 --> G3["📌 Descrição do Distrito (Hist.12)"]
    G3 --> H3["Bairros atendidos
    População
    Unidades de referência"]
    
    %% Conexões cruzadas
    I1 --> G2
    F3 --> G2
    F3 --> I1
    H3 --> E2
    
    classDef historia fill:#e3f2fd,stroke:#0d47a1,stroke-width2px;
    class C1,C2,C3,C4 historia;
```

**Legenda:**  
📍 Geolocalização | 🏙️ Filtros regionais | 🩺 Especialidades | 📚 Educação em saúde  
ℹ️ Informações detalhadas | 🌐 Dados territoriais | 📅 Horários atualizados

> **Requisitos atendidos:** Todas as 12 histórias de usuário integradas em fluxos complementares.
