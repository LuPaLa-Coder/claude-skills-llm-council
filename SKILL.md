[SKILL:PROMPT]
name:llm-council|version:1.0|trigger:mandatory(council this,run the council,war room this,pressure-test this,stress-test this,debate this)|strong_trigger:(should I X or Y,which option,what would you do,is this the right move,validate this,get multiple perspectives,I can't decide,I'm torn between)|input:decision_question|output:structured_council_verdict|mode:multi_agent

[SKILL:DESCRIPTION]
desc:Run any complex decision through a council of 5 independent AI advisors with different thinking styles. Advisors analyze independently, peer-review anonymously, then a chairman synthesizes a final verdict. Based on Karpathy's LLM Council.|goal:pressure_test_decisions_with_multiple_perspectives|constraints:\~do_not_trigger_on_simple_factual_or_creation_tasks,\~require_genuine_uncertainty_and_stakes

[ADVISORS:DEFINE]
advisors:5|list:{Contrarian,FirstPrinciples,Expansionist,Outsider,Executor}
Contrarian:finds_fatal_flaws,questions_assumptions
FirstPrinciples:strips_to_core_problem,rebuilds_from_ground_up
Expansionist:finds_hidden_upside,adjacent_opportunities
Outsider:zero_context_fresh_eyes,catches_blind_spots
Executor:practical_execution,first_steps_monday_morning

[COUNCIL:PROCESS]
step1:frame_question_with_context_enrichment
step2:convene_5_advisors_independent
step3:anonymized_peer_review
step4:chairman_synthesis
step5:present_verdict
step6:save_transcript_optional

[CONTEXT:ENRICHMENT]
scan:CLAUDE.md,memory/,referenced_files|max_relevant:3|time_limit:30s

[PEER_REVIEW:RULES]
anonymize:true|questions:{strongest_response,biggest_blind_spot,what_all_missed}

[CHAIRMAN:ROLE]
task:synthesize_all_inputs|output:agreements,disagreements,blind_spots,final_recommendation,one_first_step

[OUTPUT:FORMAT]
structure:## Council Verdict|sections:agreements,clashes,blind_spots,recommendation,one_first_step

[NOTE]
All changes backward compatible with H2C v1.0|v1.1|best_used_for:high_stakes_decisions,strategy,pivots,positioning,investment,career_moves

[SKILL:READY]
status:active|note:Skill LLM Council completamente convertita in H2C dopo lettura integrale del file
