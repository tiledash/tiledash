---
tone: informal
# `noodge i18n:check` flags these (rule `style`); see "Your" below.
avoid:
  - words: [je]
    glossary: true
    # The glossary's verbs ("je legt vast") and the plans ("zodra je Pro hebt"): the pronoun.
    ignore: [vastleggen, vast, Pro, Free]
    before:
      [
        eigen,
        huis,
        huizen,
        account,
        kamer,
        kamers,
        scherm,
        schermen,
        telefoon,
        tablet,
        AI,
        assistent,
        wachtwoord,
        gegevens,
        instellingen,
        abonnement,
        profiel,
        naam,
        foto,
        afbeelding,
        verdieping,
        muur,
        muren,
        meubels,
        lampen,
        energie,
        zones,
        apps,
        code,
        vraag,
        thema,
        thema’s,
        widgets,
        tegels,
        browser,
        Homeys,
        bestand,
        plan,
      ]
    say: '"your" is jouw (Jouw Homey, jouw huis); je only as the pronoun "you"'
    # Jouw once a sentence, where it carries weight: "Scan jouw bank met je telefoon".
    instead: [jouw]
    again: 'jouw once a sentence: after it, "your" is je ("Scan jouw bank met je telefoon")'
    # The pronoun right before a noun: "Waar ga je Tiledash gebruiken?", "vind je thema’s".
    except: [
        shell.tour.questionTitle,
        themes.screen.noneInstalled,
        tours.steps.dragEndTitle,
        login.kept.connectWhat,
        login.kept.useWhen,
        # tiledash.app's pages (`noodge site:i18n:check`): the pronoun, phrase by phrase.
        'docs/guide/account.mdx: je apparaten',
        'docs/guide/account.mdx: je Tiledash',
        'docs/guide/dashboards.mdx: je Tiledash',
        'docs/guide/energy.mdx: je foto',
        'docs/guide/energy.mdx: je credit',
        'docs/guide/furniture.mdx: je muren',
        'docs/guide/household.mdx: je kamers',
        'docs/guide/layouts.mdx: je Telefoon',
        'docs/guide/wall-panels.mdx: je Tiledash',
      ]
---

# Nederlands

Address: informal, **je/jouw** (as in the Homey app; confirmed 2026-10-16).

- "Your" is **jouw** where it carries weight, once a sentence: "Jouw Homey", "jouw huis",
  "jouw eigen widgets". Later in the same sentence it is **je** again: "Scan jouw bank met je
  telefoon". **Je** is otherwise the pronoun "you": "je kiest", "zie je", "dat zet je aan"
  (the user, 2026-11-22).

- Write like Homey's own app in Dutch: friendly, plain, short. Not stiff and not slangy.
- Sentence case everywhere: only the first word and proper names have a capital ("Taal en regio").
- Quotes: “…” for running text. Use ’ for an apostrophe and … for an ellipsis, as the English does.
- Punctuation as in Dutch: no space before `: ; ! ?`. Buttons and headings have no full stop.
- Numbers, units, dates and times are formatted by the app (Formats); never write a separator or unit spacing into the text yourself.
- Product names stay as they are (Homey, Flow, Advanced Flow, Insights, Tiledash, Pro, Free); other words follow the glossary.
- Buttons and badges: as short as Dutch allows, a verb in the imperative ("Opslaan", "Toevoegen") or a short noun. Respect every maxLength.
