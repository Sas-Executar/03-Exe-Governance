# UIX Design System — WI MAP / REPORT

**Profile:** `wi_map_report_uix.akw.v2`  
**Handoff:** `uix/DESIGN_HANDOFF.md`

## Fluxo de aplicação

```text
PAYLOAD → JSON SCHEMA → TEMPLATE → UIX TOKENS → COMPONENTES → VALIDAÇÃO → MAP/REPORT
```

A UIX não adiciona campos de negócio. Ela transforma os layouts em uma família visual única, com estados semânticos explícitos, SVGs, responsividade e impressão previsível.

## Tokens-chave
- `brand_primary`: #3157C8
- `inverse_surface`: #121B34
- `gate`: #C95D32
- `complete`: #16876F
- `canvas`: #F4F7FB
- `border`: #E4E8F0

## Regra para novos templates
1. Registrar `data-uix-profile`.
2. Reutilizar tokens semânticos.
3. Não introduzir cores literais fora da camada de tokens.
4. Não usar imagens raster para controles/ícones.
5. Preservar labels textuais para todos os estados.


## Override AKW v2.0

Conclusão usa `exec.color.done` (azul). Radius de objetos e controles são distintos. Prismas usam trim 10 mm, área útil 190×277 mm e faces de 92,333 mm.
