
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>스피드 영어 퀴즈 (Week 13~18)</title>
    <style>
        body { font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif; background-color: #f0f4f8; color: #333; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; padding: 20px; box-sizing: border-box; }
        .container { background: white; padding: 30px; border-radius: 16px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); max-width: 650px; width: 100%; }
        h1 { text-align: center; margin-bottom: 20px; color: #1e293b; font-size: 26px; }
        .week-tabs { display: flex; gap: 8px; margin-bottom: 25px; border-bottom: 2px solid #e2e8f0; padding-bottom: 10px; justify-content: center; flex-wrap: wrap; }
        .week-tab { padding: 8px 14px; border: none; background: none; font-size: 14px; font-weight: bold; color: #94a3b8; cursor: pointer; border-radius: 8px; transition: all 0.2s; }
        .week-tab.active { background-color: #e0f2fe; color: #0284c7; }
        .week-tab:hover:not(.active):not(:disabled) { background-color: #f1f5f9; }
        .week-tab:disabled { cursor: not-allowed; opacity: 0.5; }
        .category-section { margin-bottom: 25px; background: #f8fafc; padding: 20px; border-radius: 12px; border: 1px solid #e2e8f0; }
        .category-title { font-size: 18px; font-weight: bold; color: #334155; margin-top: 0; margin-bottom: 15px; display: flex; align-items: center; gap: 8px; }
        .flavor-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        @media (max-width: 480px) { .flavor-grid { grid-template-columns: 1fr; } }
        .flavor-btn { background: white; border: 2px solid #cbd5e1; border-radius: 10px; padding: 15px; text-align: left; cursor: pointer; transition: all 0.2s ease; }
        .flavor-btn:hover { border-color: #3b82f6; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.15); transform: translateY(-2px); }
        .flavor-title { font-size: 16px; font-weight: bold; display: block; margin-bottom: 6px; }
        .flavor-desc { font-size: 13px; color: #64748b; line-height: 1.4; word-break: keep-all; }
        .t-easy { color: #10b981; } .t-hard { color: #ef4444; }
        .hidden { display: none !important; }
        #quiz-area { display: flex; flex-direction: column; gap: 20px; }
        #question-counter { font-size: 15px; color: #64748b; font-weight: bold; text-align: center;}
        .question-box { font-size: 22px; font-weight: bold; word-break: keep-all; line-height: 1.5; background: #f8fafc; padding: 30px 20px; border-radius: 12px; border: 2px dashed #cbd5e1; cursor: pointer; transition: background 0.2s; text-align: center; }
        .question-box:hover { background: #e2e8f0; }
        .question-box::after { content: "(클릭하여 정답 확인)"; font-size: 13px; color: #94a3b8; display: block; margin-top: 10px; font-weight: normal; }
        .answer-box { background: #ecfdf5; padding: 25px 20px; border-radius: 12px; border: 1px solid #a7f3d0; text-align: left; }
        .en-text { font-size: 22px; color: #059669; font-weight: bold; margin-bottom: 15px; line-height: 1.4; word-break: keep-all;}
        .meta-info { font-size: 14px; color: #475569; margin-bottom: 5px; background: #fff; display: inline-block; padding: 4px 10px; border-radius: 20px; border: 1px solid #e2e8f0; }
        .meaning-info { font-size: 15px; color: #b45309; margin-bottom: 15px; background: #fef3c7; padding: 8px 12px; border-radius: 8px; font-weight: 500;}
        .controls { display: flex; justify-content: space-between; align-items: center; margin-top: 10px; flex-wrap: wrap; gap: 10px;}
        .left-controls { display: flex; gap: 10px; }
        .btn { padding: 10px 20px; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; font-size: 15px; transition: 0.2s;}
        .btn-tts { background-color: #8b5cf6; color: white; display: flex; align-items: center; gap: 5px; }
        .btn-tts:hover { background-color: #7c3aed; }
        .btn-star { background-color: #e2e8f0; color: #475569; }
        .btn-star.active { background-color: #fef08a; color: #ca8a04; border: 1px solid #fde047; }
        .btn-next { background-color: #10b981; color: white; }
        .btn-next:hover { background-color: #059669; }
        .btn-finish { background-color: #3b82f6; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 10px; }
        .btn-finish:hover { background-color: #2563eb; }
        .btn-home { background-color: #64748b; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 20px;}
        .btn-home:hover { background-color: #475569; }
        #review-area { display: flex; flex-direction: column; gap: 15px; }
        .review-card { background: #fff; border: 1px solid #e2e8f0; border-radius: 10px; padding: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); text-align: left;}
        .review-ko { font-size: 16px; font-weight: bold; color: #334155; margin-bottom: 8px; }
        .review-en { font-size: 18px; font-weight: bold; color: #059669; margin-bottom: 8px; }
        .review-empty { text-align: center; padding: 40px 20px; font-size: 18px; color: #10b981; font-weight: bold; background: #ecfdf5; border-radius: 12px;}
    </style>
</head>
<body>
<div class="container">
    <h1 id="main-title">🚀 스피드 영어 퀴즈</h1>
    <div id="mode-selection">
        <div class="week-tabs">
            <button class="week-tab" onclick="setWeek(13, this)">Week 13</button>
            <button class="week-tab" onclick="setWeek(14, this)">Week 14</button>
            <button class="week-tab" onclick="setWeek(15, this)">Week 15</button>
            <button class="week-tab" onclick="setWeek(16, this)">Week 16</button>
            <button class="week-tab" onclick="setWeek(17, this)">Week 17</button>
            <button class="week-tab active" onclick="setWeek(18, this)">Week 18</button>
            <button class="week-tab" onclick="setWeek('all', this)">Week 13~18 누적</button>
        </div>
        <div class="category-section">
            <h3 class="category-title">🧩 구동사 (Phrasal Verbs)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('phrasal-easy')"><span class="flavor-title t-easy">🟢 순한맛</span><span class="flavor-desc">구동사 의미별로 짧고 쉬운 문장들이 선별해서 담겨있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('phrasal-hard')"><span class="flavor-title t-hard">🔴 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
        <div class="category-section">
            <h3 class="category-title">🗣️ 영어회화 (Conversation)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('conv-easy')"><span class="flavor-title t-easy">💬 순한맛</span><span class="flavor-desc">'대표문장'과 '교재1'만 담고 있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('conv-hard')"><span class="flavor-title t-hard">🔥 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
    </div>
    <div id="quiz-area" class="hidden">
        <div id="question-counter">문제 1 / 10</div>
        <div class="question-box" id="ko-box" onclick="showAnswer()"><span id="ko-text">한국어 문장</span></div>
        <div class="answer-box hidden" id="answer-section">
            <div class="meta-info" id="source-info">출처</div>
            <div class="en-text" id="en-text">English Answer</div>
            <div class="meaning-info hidden" id="meaning-info">의미</div>
            <div class="controls">
                <div class="left-controls"><button class="btn btn-tts" onclick="playTTS()">🔊 듣기</button><button class="btn btn-star" id="btn-star" onclick="toggleStar()">⭐ 어려워요</button></div>
                <button class="btn btn-next" id="btn-next" onclick="nextQuestion()">다음 문제 ➡</button>
            </div>
        </div>
        <button class="btn btn-finish hidden" id="btn-finish" onclick="showReview()">결과 보기 (오답 노트) 📝</button>
    </div>
    <div id="review-area" class="hidden">
        <h2 style="text-align: center; color: #1e293b; margin-top:0;">⭐ 나의 오답 노트</h2>
        <p style="text-align: center; color: #64748b; font-size: 14px; margin-top:-10px;">어려웠던 문장들을 다시 확인해 보세요!</p>
        <div id="review-list"></div>
        <button class="btn btn-home" onclick="resetToHome()">🏠 처음으로 돌아가기</button>
    </div>
</div>
<script>
    let currentWeekFilter = 18;
    function setWeek(week, btn) {
        if (week === 'all') currentWeekFilter = 'all';
        else currentWeekFilter = parseInt(week);
        document.querySelectorAll('.week-tab').forEach(el => el.classList.remove('active'));
        btn.classList.add('active');
    }

    const meanings = {
        // Week 13
        "mess around_1": "mess around: (고장 날 위험이 있는 사물을) 자꾸 만지작거리다",
        "mess around_2": "mess around: (해야 할 일을 안 하고) 빈둥거리며 시간을 보내다",
        "mess around_3": "mess around: (진지하지 않게 가벼운 태도로) 장난치다",
        "mess around_4": "mess around: (이성과 진지하지 않은 관계를 맺으며) 시간을 허비하다",
        "mess up_1": "mess up: (실수를 저질러 상황을) 망치다",
        "mess up_2": "mess up: (깔끔했던 것을 지저분하게) 엉망으로 만들다",
        "mess with_1": "mess with: (커피 등이 수면 등에) 안 좋은 영향을 미치다, 방해하다",
        "mess with_2": "mess with: (트러블을 피하기 위해 특정인과) 더는 엮이지 않다",
        "mess with_3": "mess with: (상대를 골탕 먹이려고 장난삼아) 놀리다",
        "mess with_4": "mess with: (남의 물건이나 설정을 부주의하게 만져서) 망가뜨리다",
        "mess with_5": "mess with: (화난 사람을) 괜히 자극하다, 건드리다",
        "miss out_1": "miss out: (남들은 다 누리는) 좋은 기회나 즐거움을 놓치다",
        "move on_1": "move on: (한 장소에서 머물다가 다른 장소로) 이동하다",
        "move on_2": "move on: (하던 일을 마치고 다음 단계/질문으로) 넘어가다",
        "move on_3": "move on: (이별 후 상처를 잊고) 새로운 출발을 하다",
        "move on_4": "move on: (과거의 팬이나 지지자가) 이미 마음이 떠나버리다",
        // Week 14
        "pass for_1": "pass for: (실제와 달라도 겉보기에) ~으로 통하다, 믿어지다",
        "pass for_2": "pass for: (의도적으로) ~인 척하다, 위장하다",
        "pass up_1": "pass up: (아깝지만 불가피한 상황 때문에) 기회를 거절하다, 포기하다",
        "pick up_1": "pick up: (바닥에 있는 것을 손으로) 집어 올리다",
        "pick up_2": "pick up: (차에 태우기 위해 특정 장소로) 마중 나가다, 태우다",
        "pick up_3": "pick up: (집에 오는 길에 가벼운 물건을) 사 오다",
        "pick up_4": "pick up: (타인의 말투나 습관 등을 무의식적으로) 닮게 되다, 배우다",
        "pick up_5": "pick up: (중단되었던 대화나 일을) 멈춘 지점부터 다시 시작하다",
        "pick up on_1": "pick up on: (남들은 모르는 미묘한 변화나 뉘앙스를) 알아차리다",
        "pull off_1": "pull off: (몸에 꽉 끼는 옷 등을) 힘들게 벗다, 떼어내다",
        "pull off_2": "pull off: (소화하기 힘든 패션 등을) 멋지게 소화해 내다",
        "pull off_3": "pull off: (모두가 불가능하다고 여긴 일을) 성공시키다, 해내다",
        // Week 15
        "put away_1": "put away: (사용한 물건을 원래 있던) 제자리에 두다",
        "put away_2": "put away: (장래를 위해 돈을 꾸준히) 저축하다",
        "put away_3": "put away: (엄청난 양의 음식을 단숨에) 해치우다, 먹어 치우다",
        "put down_1": "put down: (손에 들고 있던 것을 바닥에) 내려놓다",
        "put down_2": "put down: (잊지 않기 위해 종이에) 적다, 기재하다",
        "put down_3": "put down: (예약이나 렌트를 위해 보증금을) 예치하다, 맡기다",
        "put down_4": "put down: (남들 앞에서 상대를) 무시하거나 깎아내리는 말을 하다",
        "put off_1": "put off: (하기 싫거나 준비가 안 되어 일정을) 나중으로 미루다",
        "put off_2": "put off: (안 좋은 냄새나 태도 등이 상대를) 정떨어지게 만들다",
        "put on_1": "put on: (옷/안경 등을 몸에 걸치는) '동작'을 하다",
        "have on_1": "have on: (옷/안경 등을 이미 몸에 걸치고 있는) '상태'이다",
        "try on_1": "try on: (사이즈나 어울림을 보려고) 시험 삼아 입어 보다",
        "put together_1": "put together: (부품을 모아 가구 등을) 직접 조립하다",
        "put together_2": "put together: (사람이나 아이디어를 모아 팀/계획을) 구성하다",
        "put together_3": "put together: (수치를 모두 합산하여) 다 합치다",
        // Week 16
        "put up_1": "put up: (벽이나 높은 곳에 포스터 등을) 올리다, 붙이다",
        "put up_2": "put up: (울타리나 건물 등을 토대부터) 세우다, 짓다",
        "put up_3": "put up: (SNS 등에 사진이나 게시글을) 올리다",
        "put up_4": "put up: (여행 온 사람 등을 집에서 몇 밤) 재워 주다",
        "put up with_1": "put up with: (불편한 출퇴근 등 어쩔 수 없는 상황을) 참고 견디다",
        "put up with_2": "put up with: (성격이 힘든 특정 사람의 태도를) 인내심 있게 참아주다",
        "run into_1": "run into: (실수로 사물 등에) 물리적으로 꽝 부딪히다",
        "run into_2": "run into: (길에서 아는 사람을) 우연히 마주치다",
        "run into_3": "run into: (예상치 못한 난관이나 문제에) 맞닥뜨리다",
        "settle for_1": "settle for: (최선은 아니지만 아쉬운 대로) 차선책에 만족하다",
        "show off_1": "show off: (남의 관심을 끌려고 장점을) 과시하다, 으스대다",
        "brag about_1": "brag about: (말로 자기 자랑을 늘어놓으며) 뽐내다",
        // Week 17
        "slack off_1": "slack off: (공부나 일을 안 하고) 나태하게 게으름을 피우다",
        "slack off_2": "slack off: (매출이나 기세 등이 이전보다) 약화되다, 주춤하다",
        "sort out_1": "sort out: (재활용품 등을 기준에 맞게) 알맞게 분류하다",
        "sort out_2": "sort out: (어지럽게 널브러진 물건들을) 정리하다",
        "sort out_3": "sort out: (복잡하게 얽힌 문제나 오해를) 해결하다, 해소하다",
        "sort out_4": "sort out: (여행 경로 등 세부적인 계획을) 짜다",
        "stick around_1": "stick around: (가야 할 시간임에도 그 자리에) 좀 더 머물다",
        "stick around_2": "stick around: (냄새 등이 환기되지 않고 공간에) 남다",
        "stick around_3": "stick around: (새로운 기술 등이 반짝 유행에 그치지 않고) 계속 지속되다",
        "stick it out_1": "stick it out: (힘들어도 포기하지 않고) 끝까지 버티다",
        "tough it out_1": "tough it out: (육체적/정신적 고통을 묵묵히) 참고 견뎌내다",
        "stop by_1": "stop by: (목적지로 가는 길에 아주 잠깐) 들르다",
        "come by_1": "come by: (방문을 목적으로 상대적으로 시간을 내어) 들르다",
        "drop by_1": "drop by: (정중하게 혹은 예고 없이 쑥) 방문하다, 들르다",
        "swing by_1": "swing by: (지나가는 길에 가볍고 빠르게) 휙 들르다",
        // Week 18
        "take away_1": "take away: (있던 것을 아예 없애거나) 억지로 빼앗아 가다",
        "take away_2": "take away: (영화를 보거나 대화를 한 후 특정 느낌을) 얻다, 건지다",
        "take away_3": "take away: (안 좋은 요인이 본질적인) 재미나 가치를 반감시키다",
        "take back_1": "take back: (빌린 물건을 주인에게) 다시 돌려주다, 반납하다",
        "take back_2": "take back: (방금 했던 실수나 말을) 없던 일로 취소하다",
        "take back_3": "take back: (부당하게 뺏긴 것을 힘으로) 되찾아 오다",
        "take back_4": "take back: (추억을 떠올리게 하여 옛날 생각을) 상기시키다",
        "take off_1": "take off: (몸에 걸치고 있던 옷이나 안경 등을) 벗다",
        "take off_2": "take off: (비행기가 땅을 차고 위로) 이륙하다",
        "take off_3": "take off: (급한 일이 생겨서 그 장소를) 떠나다, 출발하다",
        "take off_4": "take off: (사업이나 유행이 단기간에) 엄청난 인기를 얻다, 성공하다",
        "take off_5": "take off: (명단이나 선반 위에서 물건을) 빼다, 제외하다",
        "take off_6": "take off: (정가에서 일정 금액을) 가격 할인해주다, 빼주다",
        "take on_1": "take on: (라이벌과 시합에서) 한판 붙다, 상대로 맞서다",
        "take on_2": "take on: (과도한 업무나 책임 등을) 떠안다, 맡다",
        "take on_3": "take on: (추가적으로 학생이나 손님을) 더 받다, 채용하다",
        "take on_4": "take on: (상황에 따라 평소와 다른) 특징이나 성격을 띠다",
        "take out_1": "take out: (문장이나 성분 등을) 밖으로 빼다, 제거하다",
        "take out_2": "take out: (새 차 등을 시험 삼아 장소 밖으로) 가지고 나가다",
        "take out_3": "take out: (남에게 식사나 데이트를) 대접하다, 데리고 나가다",
        "take out_4": "take out: (은행에서 필요한 돈을) 대출받다",
        "take out_5": "take out: (남에게 자신의 화를) 분풀이하다"
    };
    // ===== 구동사 순한맛 (Week 13~18) =====
    const phrasalEasy = [
        // Week 13
        { week: 13, ko: "휴대폰 그만 만지작거려.", en: "Stop messing around with your phone.", source: "Day 061 순한맛", meaning: meanings["mess around_1"] },
        { week: 13, ko: "비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 061 순한맛", meaning: meanings["mess around_2"] },
        { week: 13, ko: "그냥 장난친 거라고.", en: "I was just trying to mess around.", source: "Day 061 순한맛", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다.", en: "I am tired of messing around.", source: "Day 061 순한맛", meaning: meanings["mess around_4"] },
        { week: 13, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 062 순한맛", meaning: meanings["mess up_1"] },
        { week: 13, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 062 순한맛", meaning: meanings["mess up_2"] },
        { week: 13, ko: "늦은 시간에 커피 마시지 말아야겠어; 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 063 순한맛", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어.", en: "I don't mess with Brandon anymore.", source: "Day 063 순한맛", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야.", en: "I was just messing with you.", source: "Day 063 순한맛", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야?", en: "Hey, did you mess with the settings on my camera?", source: "Day 063 순한맛", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 알게 되었어요.", en: "I learned the hard way not to mess with kitchen staff.", source: "Day 063 순한맛", meaning: meanings["mess with_5"] },
        { week: 13, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I'm not going to miss out on it.", source: "Day 064 순한맛", meaning: meanings["miss out_1"] },
        { week: 13, ko: "저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어.", en: "We had dinner and moved on to a quiet wine bar where we talked for hours.", source: "Day 065 순한맛", meaning: meanings["move on_1"] },
        { week: 13, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 다시 풀어 봐.", en: "Move on and try again when you've finished the easier ones.", source: "Day 065 순한맛", meaning: meanings["move on_2"] },
        { week: 13, ko: "전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "I guess she moves on really fast.", source: "Day 065 순한맛", meaning: meanings["move on_3"] },
        { week: 13, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 065 순한맛", meaning: meanings["move on_4"] },
        // Week 14
        { week: 14, ko: "재미 교포라고 해도 믿을 것이다.", en: "He can pass for a Korean-American.", source: "Day 066 순한맛", meaning: meanings["pass for_1"] },
        { week: 14, ko: "그는 정상적인 은행원인 척 거짓 삶을 살았다.", en: "He was living his life, passing for a normal banker and husband.", source: "Day 066 순한맛", meaning: meanings["pass for_2"] },
        { week: 14, ko: "세일하는 걸 그냥 지나칠 수가 없었다.", en: "I couldn't pass up (on) the sale.", source: "Day 067 순한맛", meaning: meanings["pass up_1"] },
        { week: 14, ko: "원두는 쏟으면 줍기가 번거롭다.", en: "Coffee beans are a hassle to pick up if you spill them.", source: "Day 068 순한맛", meaning: meanings["pick up_1"] },
        { week: 14, ko: "내가 회사로 태우러 갈게.", en: "I will pick you up from work.", source: "Day 068 순한맛", meaning: meanings["pick up_2"] },
        { week: 14, ko: "집에 가는 길에 저녁거리 좀 사 갈게.", en: "I'll pick up something for dinner on my way home.", source: "Day 068 순한맛", meaning: meanings["pick up_3"] },
        { week: 14, ko: "그분들 때문에 그렇게 표현하게 된 것 같아요.", en: "I think I picked up that expression from the Canadians in my office.", source: "Day 068 순한맛", meaning: meanings["pick up_4"] },
        { week: 14, ko: "어제 마친 부분부터 다시 이야기할까요?", en: "Let's pick up where we left off yesterday.", source: "Day 068 순한맛", meaning: meanings["pick up_5"] },
        { week: 14, ko: "민지는 생각보다 빠르게 언어의 뉘앙스를 알아차리더군요.", en: "Minji picked up on the nuances of the language faster than expected.", source: "Day 069 순한맛", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "청바지 벗는 게 쉽지 않다.", en: "I have a hard time pulling my jeans off after a big dinner.", source: "Day 070 순한맛", meaning: meanings["pull off_1"] },
        { week: 14, ko: "나는 소화하기 어렵다.", en: "I can't pull it off.", source: "Day 070 순한맛", meaning: meanings["pull off_2"] },
        { week: 14, ko: "할 수 있겠어?", en: "Do you think you can pull it off?", source: "Day 070 순한맛", meaning: meanings["pull off_3"] },
        // Week 15
        { week: 15, ko: "반드시 운동기구를 제자리에 두기 바랍니다.", en: "Please be sure to put away weights after you use them.", source: "Day 071 순한맛", meaning: meanings["put away_1"] },
        { week: 15, ko: "저축할 돈이 거의 남지 않아요.", en: "I don't have any money left to put away after paying all my bills.", source: "Day 071 순한맛", meaning: meanings["put away_2"] },
        { week: 15, ko: "혼자서 삼겹살 3인분을 해치우지.", en: "This mukbang YouTuber can put away three servings of pork belly by herself.", source: "Day 071 순한맛", meaning: meanings["put away_3"] },
        { week: 15, ko: "휴대폰 내려놓고 저녁 먹어야지!", en: "Put down your phone and eat your dinner!", source: "Day 072 순한맛", meaning: meanings["put down_1"] },
        { week: 15, ko: "제 생각을 적으려고 합니다.", en: "I try to put down my thoughts on paper when I have too many things to do.", source: "Day 072 순한맛", meaning: meanings["put down_2"] },
        { week: 15, ko: "보증금으로 30만원을 예치해야 합니다.", en: "We require that our customers put down a 300,000 won security deposit to rent a car.", source: "Day 072 순한맛", meaning: meanings["put down_3"] },
        { week: 15, ko: "꼭 그렇게 나를 깎아내려야 했어?", en: "Why did you have to put me down in front of everybody like that?", source: "Day 072 순한맛", meaning: meanings["put down_4"] },
        { week: 15, ko: "몇 달째 미루고 있던 복잡한 세금 서류 알지? 드디어 처리했어.", en: "You know that complicated tax paperwork I was putting off for months? I finally got around to it.", source: "Day 073 순한맛", meaning: meanings["put off_1"] },
        { week: 15, ko: "담배 냄새가 정말 정이 떨어진다.", en: "The smell of tobacco really puts me off.", source: "Day 073 순한맛", meaning: meanings["put off_2"] },
        { week: 15, ko: "그냥 모자 쓰고 가자.", en: "Just put on a hat and let's go.", source: "Day 074 순한맛", meaning: meanings["put on_1"] },
        { week: 15, ko: "양말을 안 신었네?", en: "You don't have any socks on?", source: "Day 074 순한맛", meaning: meanings["have on_1"] },
        { week: 15, ko: "결정하기 전에 입어 보려고요.", en: "I want to try this on before I decide.", source: "Day 074 순한맛", meaning: meanings["try on_1"] },
        { week: 15, ko: "직접 조립할 수 없어요.", en: "I can't put together anything that requires a drill.", source: "Day 075 순한맛", meaning: meanings["put together_1"] },
        { week: 15, ko: "우리 머리를 맞대어서 올여름 재미있는 여행 계획을 짜 보자.", en: "Let's put our heads together and plan a fun trip this summer.", source: "Day 075 순한맛", meaning: meanings["put together_2"] },
        { week: 15, ko: "이번 신규 스마트폰 모델의 첫 주 판매치가 이전 모델을 다 합친 것보다 더 많았다.", en: "The sales of this new smartphone model in its first week exceeded those of all previous models put together.", source: "Day 075 순한맛", meaning: meanings["put together_3"] },
        // Week 16
        { week: 16, ko: "포스터 붙일 멋진 곳을 방금 찾았어!", en: "I just found a great place to put up our posters!", source: "Day 076 순한맛", meaning: meanings["put up_1"] },
        { week: 16, ko: "정원에 울타리를 칠까 해요.", en: "We were thinking of putting up a fence around our garden to keep out the neighbors' dogs.", source: "Day 076 순한맛", meaning: meanings["put up_2"] },
        { week: 16, ko: "인스타에 올리자.", en: "Let's put up these pictures of the decor on Instagram before we head out.", source: "Day 076 순한맛", meaning: meanings["put up_3"] },
        { week: 16, ko: "Jeff가 몇 주간 재워 줬답니다.", en: "Jeff put me up for a few weeks.", source: "Day 076 순한맛", meaning: meanings["put up_4"] },
        { week: 16, ko: "출퇴근을 언제까지 견딜 수 있을지 모르겠어요.", en: "I don't know how long I can put up with this two-hour commute every day.", source: "Day 077 순한맛", meaning: meanings["put up with_1"] },
        { week: 16, ko: "네 아내가 너를 어떻게 참지?", en: "How does your wife put up with you?", source: "Day 077 순한맛", meaning: meanings["put up with_2"] },
        { week: 16, ko: "결국 회전문에 부딪히고 말았어요.", en: "I was staring at my phone and ended up running into the revolving door.", source: "Day 078 순한맛", meaning: meanings["run into_1"] },
        { week: 16, ko: "여기서 보다니 반갑다!", en: "Nice running into you!", source: "Day 078 순한맛", meaning: meanings["run into_2"] },
        { week: 16, ko: "착륙 직전에 난기류를 만났습니다.", en: "We ran into some turbulence just before landing.", source: "Day 078 순한맛", meaning: meanings["run into_3"] },
        { week: 16, ko: "그냥 작년 모델에 만족해야 했어요.", en: "I just settled for last year's model, instead.", source: "Day 079 순한맛", meaning: meanings["settle for_1"] },
        { week: 16, ko: "여자애들에게 잘 보이려고 그러는 거지.", en: "He's trying to show off to impress some girls.", source: "Day 080 순한맛", meaning: meanings["show off_1"] },
        { week: 16, ko: "남자가 밤새 자기 자랑을 하더라고.", en: "The guy just bragged about himself the whole night.", source: "Day 080 순한맛", meaning: meanings["brag about_1"] },
        // Week 17
        { week: 17, ko: "게으름 피우지 않으려고 노력 중입니다.", en: "I've been trying to stop slacking off.", source: "Day 081 순한맛", meaning: meanings["slack off_1"] },
        { week: 17, ko: "매출이 주춤하고 있습니다.", en: "Sales are slacking off.", source: "Day 081 순한맛", meaning: meanings["slack off_2"] },
        { week: 17, ko: "재활용품을 분류해야 해.", en: "Sort out all the recycling before going outside.", source: "Day 082 순한맛", meaning: meanings["sort out_1"] },
        { week: 17, ko: "물건들을 좀 정리해야겠어.", en: "My room is a terrible mess, so I need to sort it out.", source: "Day 082 순한맛", meaning: meanings["sort out_2"] },
        { week: 17, ko: "다 잘 해결된 거야?", en: "Did you get everything sorted out?", source: "Day 082 순한맛", meaning: meanings["sort out_3"] },
        { week: 17, ko: "최대한 빨리 휴가 일정을 짜야 해.", en: "We need to sort out our holiday itinerary as soon as possible.", source: "Day 082 순한맛", meaning: meanings["sort out_4"] },
        { week: 17, ko: "좀 더 앉아 있다가 가자.", en: "Let's stick around for a while.", source: "Day 083 순한맛", meaning: meanings["stick around_1"] },
        { week: 17, ko: "냄새가 몇 시간이나 남아 있거든요.", en: "The smell still sticks around for hours.", source: "Day 083 순한맛", meaning: meanings["stick around_2"] },
        { week: 17, ko: "가상현실 홈트레이닝이 그리 오래갈 것 같지는 않다.", en: "I don't think they'll stick around for long.", source: "Day 083 순한맛", meaning: meanings["stick around_3"] },
        { week: 17, ko: "끝까지 포기하지 않으면 정규직이 될 거야.", en: "All you need to do is stick it out until the end and you'll be a full-time employee.", source: "Day 084 순한맛", meaning: meanings["stick it out_1"] },
        { week: 17, ko: "그냥 어떻게든 이겨 내는 수밖에 없대.", en: "She basically just said that my wife needs to tough it out.", source: "Day 084 순한맛", meaning: meanings["tough it out_1"] },
        { week: 17, ko: "은행에 들러 현금 좀 찾아 올 수 있을까?", en: "Could you stop by the bank and get some cash?", source: "Day 085 순한맛", meaning: meanings["stop by_1"] },
        { week: 17, ko: "시간 될 때 들러.", en: "You should come by for a visit sometime.", source: "Day 085 순한맛", meaning: meanings["come by_1"] },
        { week: 17, ko: "세탁소에 들러서 제 양복 좀 찾아 주실 수 있을까요?", en: "Could you please drop by the cleaners and pick up my suit?", source: "Day 085 순한맛", meaning: meanings["drop by_1"] },
        { week: 17, ko: "네가 들러 주면 좋겠어, 안 바쁘면.", en: "It'd be nice if you could swing by, if you're not busy.", source: "Day 085 순한맛", meaning: meanings["swing by_1"] },
        // Week 18
        { week: 18, ko: "부모님이 내 휴대폰을 빼앗아 갔다.", en: "My parents took my phone away.", source: "Day 086 순한맛", meaning: meanings["take away_1"] },
        { week: 18, ko: "영화를 본 후 우울한 기분이 들었다.", en: "I took away a feeling of melancholy after watching the movie.", source: "Day 086 순한맛", meaning: meanings["take away_2"] },
        { week: 18, ko: "날씨가 안 좋아서 해변에서의 휴가 즐거움이 반감되었다.", en: "The bad weather really took away from our beach vacation.", source: "Day 086 순한맛", meaning: meanings["take away_3"] },
        { week: 18, ko: "잊어버리기 전에 지금 가져다드려야겠다.", en: "I'll take them back now, before I forget again.", source: "Day 087 순한맛", meaning: meanings["take back_1"] },
        { week: 18, ko: "내가 한 말 취소할게.", en: "I take that back.", source: "Day 087 순한맛", meaning: meanings["take back_2"] },
        { week: 18, ko: "내가 다시 가져갈 거야.", en: "I'm going to take back the money you stole from me.", source: "Day 087 순한맛", meaning: meanings["take back_3"] },
        { week: 18, ko: "이 사진들을 보니 옛날 생각이 나네요.", en: "Looking at these pictures really takes me back.", source: "Day 087 순한맛", meaning: meanings["take back_4"] },
        { week: 18, ko: "너는 안경 벗으면 완전 딴 사람 같아 보여.", en: "You look like a different person when you take off your glasses.", source: "Day 088 순한맛", meaning: meanings["take off_1"] },
        { week: 18, ko: "15분 후에 비행기가 이륙한다는 기장의 안내 방송은 너무나 다행스러웠다.", en: "It was such a relief to hear that the plane was going to take off in 15 minutes.", source: "Day 088 순한맛", meaning: meanings["take off_2"] },
        { week: 18, ko: "우리는 지금 출발하려고 해.", en: "We're going to take off so we can make it to the movie on time.", source: "Day 088 순한맛", meaning: meanings["take off_3"] },
        { week: 18, ko: "탕후루가 몇 달 동안 엄청 인기였어.", en: "Tanghuru really took off for a few months.", source: "Day 088 순한맛", meaning: meanings["take off_4"] },
        { week: 18, ko: "이 물건들은 선반에서 빼야 합니다.", en: "We need to take these items off the shelf.", source: "Day 088 순한맛", meaning: meanings["take off_5"] },
        { week: 18, ko: "10달러를 더 빼 드리겠습니다.", en: "We will take an additional ten dollars off.", source: "Day 088 순한맛", meaning: meanings["take off_6"] },
        { week: 18, ko: "한국이 이란과 붙었다.", en: "Korea took on Iran in the Asian cup.", source: "Day 089 순한맛", meaning: meanings["take on_1"] },
        { week: 18, ko: "내가 일을 너무 많이 떠맡았어.", en: "I have taken on too much work.", source: "Day 089 순한맛", meaning: meanings["take on_2"] },
        { week: 18, ko: "추가 학생은 못 받을 것 같네요.", en: "I don't think I could possibly take on anyone else.", source: "Day 089 순한맛", meaning: meanings["take on_3"] },
        { week: 18, ko: "그녀는 사무실에서는 완전 딴 사람이 된다.", en: "She takes on a whole different personality when she's in the office.", source: "Day 089 순한맛", meaning: meanings["take on_4"] },
        { week: 18, ko: "이 문장은 빼세요.", en: "I want you to take out this line.", source: "Day 090 순한맛", meaning: meanings["take out_1"] },
        { week: 18, ko: "차를 한 바퀴 돌아 봤는데요.", en: "I took it out for a spin and was blown away by its performance.", source: "Day 090 순한맛", meaning: meanings["take out_2"] },
        { week: 18, ko: "그분들이 청담에 있는 고급 식당에 가서 식사 대접을 해 주더군요.", en: "They took me out to a fancy restaurant in Cheongdam.", source: "Day 090 순한맛", meaning: meanings["take out_3"] },
        { week: 18, ko: "대출을 좀 받아야만 했습니다.", en: "I had to take out some loans to buy this apartment.", source: "Day 090 순한맛", meaning: meanings["take out_4"] },
        { week: 18, ko: "나한테 화풀이하지 마!", en: "Don't take your anger out on me!", source: "Day 090 순한맛", meaning: meanings["take out_5"] }
    ];
    // ===== 구동사 매운맛 (Week 13~17은 기존, Week 18 추가) =====
    const phrasalHard = [
        // Week 13 (condensed key examples)
        { week: 13, ko: "아빠가 쓰는 공구들 가지고 장난 그만 좀 쳐! 위험한 것들이 있단 말이야.", en: "Don't mess around with your dad's tools! Some of them are dangerous.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "오후 내내 보고서 마무리는 안 하고 휴대폰 하는 데 시간을 허비했다.", en: "I spent the whole afternoon messing around with my phone instead of finishing my report.", source: "Day 061 교재1", meaning: meanings["mess around_2"] },
        { week: 13, ko: "미안해. (네) 기분 상하게 할 의도는 없었어. 그냥 장난친 거라고.", en: "I'm sorry. I didn't mean for you to take that as an insult. I was just trying to mess around.", source: "Day 061 교재1", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다. 정착해서 몇 년 안에 결혼하고 싶네요.", en: "I am tired of messing around. I want to settle down and get married within the next few years.", source: "Day 061 교재1", meaning: meanings["mess around_4"] },
        { week: 13, ko: "솔직히 출근하기가 너무 싫어서 출근 전에 30분 정도 뭉그적거리는 버릇이 있다.", en: "Honestly, before leaving for work, I tend to mess around for like 30 minutes because I just don't want to go.", source: "Day 061 교재3", meaning: meanings["mess around_2"] },
        { week: 13, ko: "연습하는 동안 계속 이 춤 동작을 실수하게 된다. 이번 주말 무대에서도 내가 실수할까 봐 우리 팀원들이 걱정하고 있다.", en: "I keep messing up this particular dance move during practice. My team is getting worried that I might mess up on stage this weekend, too.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "내 머리 좀 만지지 마. (자꾸 만지면) 엉망이 될 거야. 아침에 20분이나 들여서 머리 예쁘게 만졌단 말이야.", en: "Stop touching my hair. You are gonna mess it up. I spent 20 minutes this morning getting it just right.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "4일 동안 토론토에 있었고 회의는 잘 끝났지만, 출장에서 돌아온 후 계속 수면이 엉망인 상태가 이어지고 있다.", en: "I was there for four days and the meetings went fine, but my sleep has been messed up ever since I got back.", source: "Day 062 교재3", meaning: meanings["mess up_2"] },
        { week: 13, ko: "음악 좀 바꿔 줄래? 기분이 우울해지잖아.", en: "Can you change the music? It's messing with my mood.", source: "Day 063 교재1", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어(안 놀아). 내 화를 돋워 싸움을 시작하게 하는 말만 한다니까.", en: "I don't mess with Brandon anymore. He knows exactly what to say to rile me up and start a fight.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야. 너무 예민하게 굴지 마.", en: "I was just messing with you. Don't be so sensitive.", source: "Day 063 교재1", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야? 새로 찍은 사진이 죄다 과다 노출로 나오잖아.", en: "Hey, did you mess with the settings on my camera? All my new photos are overexposed.", source: "Day 063 교재1", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 비싼 대가를 치르고 알게 되었어요. 다음 날 식중독으로 병원 신세를 지게 되었습니다.", en: "I learned the hard way not to mess with kitchen staff. I ended up in the hospital with food poisoning the next day.", source: "Day 063 교재1", meaning: meanings["mess with_5"] },
        { week: 13, ko: "우선 수면의 질을 떨어뜨립니다.", en: "First and foremost, alcohol really messes with your quality of sleep.", source: "Day 063 교재3", meaning: meanings["mess with_1"] },
        { week: 13, ko: "A: 정말 안됐다! 너무 좋은 기회를 놓쳤네! 정말 멋진 시간이었는데.", en: "A: Too bad! You really missed out! It was an amazing time.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "친구들이 끊임없이 휴가를 보내거나 밤에 나가서 노는 걸 보면 다른 사람들은 인생을 충분히 즐기는데 나만 소외된 느낌이 든다.", en: "Seeing my friends constantly on holiday or enjoying nights out can make me feel like I am missing out while others are living their life to the fullest.", source: "Day 064 교재3", meaning: meanings["miss out_1"] },
        { week: 13, ko: "지하철에서 우연히 전 여자 친구를 마주쳤는데도 아무렇지도 않더군요. 그제서야 이제는 잊고 새출발해도 되겠구나 싶었습니다.", en: "I knew I was ready to move on when I ran into my ex on the subway and I felt completely normal around her.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "이제 그녀의 전성기는 끝난 것 같다. 왜 많은 팬들이 마음이 떠나고 있는지 알겠다.", en: "It looks like her peak time in the spotlight is over, and I can see why many fans are moving on.", source: "Day 065 교재3", meaning: meanings["move on_4"] },
        // Week 14
        { week: 14, ko: "민수는 영어를 너무 잘해서 재미 교포라고 해도 믿을 것이다.", en: "Minsu's English is so good that he can pass for a Korean-American.", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "의상은 형편없었지만, 다행히 산타인 척 속일 수 있었고, 그날 저녁은 정말 신비로운 밤이었다.", en: "Despite the bad costume, I managed to pass for Santa, and the evening was a magical one.", source: "Day 066 교재3", meaning: meanings["pass for_2"] },
        { week: 14, ko: "새 옷이 필요하지는 않았지만 세일하는 걸 그냥 지나칠 수가 없었다.", en: "Even though I didn't need a new dress, I couldn't pass up (on) the sale.", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "그럴 경우 (아쉽지만) 이번 기회를 그냥 보내야 할 것 같고요. 그래도 좋은 밴인 것 같기는 합니다.", en: "If so, I will have to pass it up, even though it looks like a nice van.", source: "Day 067 교재3", meaning: meanings["pass up_1"] },
        { week: 14, ko: "야간 근무하면서 야식하는 나쁜 습관이 생긴 것 같아.", en: "It seems like I've picked up a bad habit of late-night snacking from working the night shift.", source: "Day 068 교재2", meaning: meanings["pick up_4"] },
        { week: 14, ko: "너무 잘됐다! 그럼 당신이 (마중) 나간 동안 나는 마트에 들러서 장을 좀 볼게.", en: "Well, that turned out perfectly! I am going to swing by the store to pick up some groceries while you are out, then.", source: "Day 068 교재3", meaning: meanings["pick up_3"] },
        { week: 14, ko: "서로의 얼굴을 볼 수 있으면 수업 내용을 파악하기가 훨씬 더 쉬워집니다.", en: "It's so much easier for them to pick up on what's being communicated if we can see each other's faces.", source: "Day 069 교재3", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "머리를 파란색 염색할까 고민 중인데, 내가 소화할 수 있을지 모르겠네. 나한테 어울릴까?", en: "I've been thinking about dyeing my hair blue, but I'm not sure I can pull it off. Do you think it would suit me?", source: "Day 070 교재2", meaning: meanings["pull off_2"] },
        { week: 14, ko: "전반에 2점 차이로 지고 있었지만, 후반에 손흥민 선수가 해트 트릭을 성공했다.", en: "In the first half they were down by two goals, but Son pulled off a hat trick in the second half.", source: "Day 070 교재3", meaning: meanings["pull off_3"] },
        // Week 15
        { week: 15, ko: "이 먹방 유튜버는 혼자서 삼겹살 3인분을 해치우지. 그러고도 후식 먹을 배는 따로 있어.", en: "This mukbang YouTuber can put away three servings of pork belly by herself and still has room for dessert.", source: "Day 071 교재1", meaning: meanings["put away_3"] },
        { week: 15, ko: "신형 아이패드를 사려고 그동안 돈을 모아 왔어. 그런데 그걸 보러 애플 매장에 갔더니 출시 이틀 만에 이미 다 팔렸더라.", en: "I've been putting away money for this new iPad, but when I went to the Apple Store to check one out, I found that they sold out just two days after launch.", source: "Day 071 교재1", meaning: meanings["put away_2"] },
        { week: 15, ko: "저는 할 일이 너무 많을 때는 종이에 제 생각을 적으려고 합니다. 정리하는 데 도움이 됩니다.", en: "I try to put down my thoughts on paper when I have too many things to do. It helps me get organized.", source: "Day 072 교재1", meaning: meanings["put down_2"] },
        { week: 15, ko: "모든 사람들이 있는 데서 꼭 그렇게 나를 깎아내려야 했어?", en: "Why did you have to put me down in front of everybody like that?", source: "Day 072 교재1", meaning: meanings["put down_4"] },
        { week: 15, ko: "이번 여름에 남미에 정말 가고 싶은데, 뉴스 보니까 최근에 위험한 모기 매개 바이러스가 유행한다고 하네. 그래서 남미 여행을 미루기로 했어.", en: "I really want to go to South America this summer, but the news is saying there's a dangerous mosquito-borne virus going around these days, so I decided to put that trip off.", source: "Day 073 교재1", meaning: meanings["put off_1"] },
        { week: 15, ko: "담배 냄새가 너무 싫어서 흡연자와는 절대 사귀지 않아요.", en: "I would never date a smoker because the smell of tobacco really puts me off.", source: "Day 073 교재1", meaning: meanings["put off_2"] },
        { week: 15, ko: "스웨터를 두 개 나 입고 있는데도 얼어 죽겠다.", en: "Even though I have two sweaters on, I am still freezing.", source: "Day 074 교재1", meaning: meanings["have on_1"] },
        { week: 15, ko: "항상 먼저 입어 보고 구매하는 것이 좋습니다.", en: "It's always a good idea to try something on before you buy it.", source: "Day 074 교재1", meaning: meanings["try on_1"] },
        { week: 15, ko: "제 아내는 늘 냉장고에 있는 남은 음식으로 멋진 요리를 만들어냅니다.", en: "My wife always manages to put together amazing meals with leftovers in the fridge.", source: "Day 075 교재1", meaning: meanings["put together_2"] },
        { week: 15, ko: "매년 파리를 찾는 관광객 수가 로마, 아테네, 베를린을 합친 것보다 더 많다.", en: "The number of tourists visiting Paris annually is more than those visiting Rome, Athens, and Berlin put together.", source: "Day 075 교재1", meaning: meanings["put together_3"] },
        // Week 16
        { week: 16, ko: "저희 아파트를 리모델링하는 동안 Jeff가 몇 주간 재워 줬답니다.", en: "When my apartment was being renovated, Jeff put me up for a few weeks.", source: "Day 076 교재1", meaning: meanings["put up_4"] },
        { week: 16, ko: "미네소타에서 몇 년을 살고 나서, 더는 겨울을 견디기 힘들다고 판단하고 플로리다로 이사했습니다.", en: "After years of living in Minnesota, I decided I couldn't put up with the winters anymore, and moved to Florida.", source: "Day 077 교재1", meaning: meanings["put up with_1"] },
        { week: 16, ko: "제가 십 대 때 부모님이 저를 어떻게 참아 주셨는지 모르겠어요. 정말 문제아였거든요.", en: "I don't know how my parents put up with me during my teenage years. I was a handful.", source: "Day 077 교재1", meaning: meanings["put up with_2"] },
        { week: 16, ko: "착륙 직전에 난기류를 만났습니다.", en: "We ran into some turbulence just before landing.", source: "Day 078 교재1", meaning: meanings["run into_3"] },
        { week: 16, ko: "오늘 아침에 배송이 되었을 때 설치 기사분들이 예상치 못한 문제에 부딪혔다.", en: "But then, when it finally came this morning, the guys installing it ran into a problem.", source: "Day 078 교재3", meaning: meanings["run into_3"] },
        { week: 16, ko: "원래는 좀 더 최신 모델을 원했는데 너무 비싸더라고요. 그래서 작년 모델에 만족해야 했어요.", en: "I wanted the newer model, but it was way out of my price range. I just settled for last year's model, instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "신혼여행을 유럽으로 가고 싶었지만 여행 제한 시기에 결혼을 하는 바람에 제주도에 만족할 수밖에 없었다.", en: "We wanted to go to Europe for our honeymoon, but since we got married during travel restrictions, we had to settle for Jeju Island instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "어서 하와이에 가서 (나의) 새로 만든 비키니 몸매를 과시하고 싶어!", en: "I can't wait to show off my new bikini body in Hawaii!", source: "Day 080 교재2", meaning: meanings["show off_1"] },
        { week: 16, ko: "달리 말해, 자신이 이룬 것에 대해 자랑하는 것을 주저하지 마세요.", en: "In other words, don't be shy about bragging about your accomplishments.", source: "Day 080 교재3", meaning: meanings["brag about_1"] },
        // Week 17
        { week: 17, ko: "오후 내내 보고서 마무리는 안 하고 휴대폰 하는 데 시간을 허비했다.", en: "I spent the whole afternoon messing around with my phone instead of finishing my report.", source: "Day 081 교재1", meaning: meanings["mess around_2"] },
        { week: 17, ko: "4일 동안 토론토에 있었고 회의는 잘 끝났지만, 출장에서 돌아온 후 계속 수면이 엉망인 상태가 이어지고 있다.", en: "I was there for four days and the meetings went fine, but my sleep has been messed up ever since I got back.", source: "Day 082 교재3", meaning: meanings["mess up_2"] },
        { week: 17, ko: "우선 수면의 질을 떨어뜨립니다.", en: "First and foremost, alcohol really messes with your quality of sleep.", source: "Day 083 교재3", meaning: meanings["mess with_1"] },
        { week: 17, ko: "친구들이 끊임없이 휴가를 보내거나 밤에 나가서 노는 걸 보면 다른 사람들은 인생을 충분히 즐기는데 나만 소외된 느낌이 든다.", en: "Seeing my friends constantly on holiday or enjoying nights out can make me feel like I am missing out while others are living their life to the fullest.", source: "Day 084 교재3", meaning: meanings["miss out_1"] },
        { week: 17, ko: "지하철에서 우연히 전 여자 친구를 마주쳤는데도 아무렇지도 않더군요. 그제서야 이제는 잊고 새출발해도 되겠구나 싶었습니다.", en: "I knew I was ready to move on when I ran into my ex on the subway and I felt completely normal around her.", source: "Day 085 교재1", meaning: meanings["move on_3"] },
        // Week 18 - take away
        { week: 18, ko: "내 거짓말로 인해 부모님이 내 휴대폰을 빼앗아 갔다.", en: "My parents took my phone away for lying to them.", source: "Day 086 교재1", meaning: meanings["take away_1"] },
        { week: 18, ko: "그 친구 외모 빼면, 다른 사람이랑 별반 다를 게 없죠.", en: "If you take away her looks, she's really just like everyone else.", source: "Day 086 교재1", meaning: meanings["take away_1"] },
        { week: 18, ko: "《도둑맞은 집중력》의 주제는 너무 좋았습니다. 제가 집중력에 심각한 문제가 있고, 잠도 잘 못 자거든요. 하지만 책에서 해결책은 얻지 못했어요.", en: "I loved the subject of Stolen Focus. I have some real problems focusing and getting enough sleep. However, I didn't take away any solutions from it.", source: "Day 086 교재1", meaning: meanings["take away_2"] },
        { week: 18, ko: "날씨가 안 좋아서 해변에서의 휴가 즐거움이 반감되었다.", en: "The bad weather really took away from our beach vacation.", source: "Day 086 교재1", meaning: meanings["take away_3"] },
        { week: 18, ko: "3시간 강좌 후에 선생님이 강좌에서 가장 인상 깊었던 핵심 내용 목록을 만들라고 했다.", en: "After a 3-hour lecture, the teacher asked us to make a list of the key ideas we took away from the lesson.", source: "Day 086 교재1", meaning: meanings["take away_2"] },
        { week: 18, ko: "파티가 제법 좋았지만, (파티를) 주최한 부부가 거의 파티 내내 싸우는 바람에 즐거움이 반감되었다.", en: "The party was pretty good, but the couple that was hosting fought pretty much the whole time. That took away from our enjoyment.", source: "Day 086 교재1", meaning: meanings["take away_3"] },
        { week: 18, ko: "John이 어젯밤에 또 음주 운전으로 걸렸어. 이번이 세 번째라서 경찰이 결국 면허증을 압수해 버렸지.", en: "Last night, John was pulled over after drinking and driving again. It was his third time, so they finally took away his license.", source: "Day 086 교재1", meaning: meanings["take away_1"] },
        { week: 18, ko: "우리 아들이 영어 학원을 가야 할 때 PC방에 몰래 가는 걸 봤어. 어떻게든 혼을 내야 하는데, 어떻게 해야 할지 모르겠네.", en: "I caught my son sneaking off to the PC room when he was supposed to be going to his English academy. I need to punish him somehow, but I'm not really sure what to do.", source: "Day 086 교재2", meaning: null },
        { week: 18, ko: "휴대폰을 뺏고, 몇 주간 컴퓨터를 못하게 하는 건 어때? 그래야 정신 차릴 것 같은데.", en: "What about taking away his phone and computer benefits for a few weeks? Maybe that will teach him a lesson.", source: "Day 086 교재2", meaning: meanings["take away_1"] },
        { week: 18, ko: "해산물은 신선했어. 그런데 가격이 터무니없어서 식사를 망쳤어.", en: "The seafood was fresh, but the outrageous prices took away from the meal.", source: "Day 086 교재2", meaning: meanings["take away_3"] },
        { week: 18, ko: "제 면허증을 빼앗아 가는 건 도저히 이해가 되지 않습니다.", en: "Taking away my driver's license makes no sense.", source: "Day 086 교재3", meaning: meanings["take away_1"] },
        // Week 18 - take back
        { week: 18, ko: "A: 숙모님한테 빌린 신발 돌려 드렸어? B: 아, 아니! 알려 줘서 고마워. 잊어버리기 전에 지금 가져다드려야겠다.", en: "A: Did you take those shoes back to your aunt after you borrowed them? B: Oh, no! Thanks for the reminder. I'll take them back now, before I forget again.", source: "Day 087 교재1", meaning: meanings["take back_1"] },
        { week: 18, ko: "잠시만, 내가 한 말 취소할게. 그런 의도는 아니었어.", en: "Wait, I take that back. I didn't mean it like that.", source: "Day 087 교재1", meaning: meanings["take back_2"] },
        { week: 18, ko: "이 사진들을 보니 옛날 생각이 나네요. 지금 보면 텍사스 시절이 근심 걱정없어 보이지만, 사실은 그렇지 않았어요.", en: "Looking at these pictures really takes me back. Those days in Texas seem so carefree now, but I know it's not real.", source: "Day 087 교재1", meaning: meanings["take back_4"] },
        { week: 18, ko: "이 스웨터를 반품하시려면 영수증이 있어야 합니다.", en: "You need the receipt if you want to take your sweater back.", source: "Day 087 교재1", meaning: meanings["take back_1"] },
        { week: 18, ko: "네가 바보 같다고 해서 미안해. 취소할게.", en: "I'm sorry that I said you were stupid. I take it back.", source: "Day 087 교재1", meaning: meanings["take back_2"] },
        { week: 18, ko: "네가 나한테서 훔쳐 간 돈 내가 다시 가져갈 거야.", en: "I'm going to take back the money you stole from me.", source: "Day 087 교재1", meaning: meanings["take back_3"] },
        { week: 18, ko: "죄송합니다. 다시 가져가서 바로 다른 것으로 만들어 오겠습니다.", en: "Oh, I'm sorry about that. I'll take it back and get another one cooked for you right away.", source: "Day 087 교재2", meaning: meanings["take back_1"] },
        { week: 18, ko: "이런 노래를 들으면 십 대 때로 돌아간 것 같아. '블랙핑크'와 '뉴진스' 노래도 좋지만, 솔직히 가사에 공감이 잘 안되거든.", en: "There is something about songs like this that takes me back to my teens. I like Blackpink and New Jeans songs, but I can't really relate to the lyrics, honestly.", source: "Day 087 교재2", meaning: meanings["take back_4"] },
        { week: 18, ko: "TV로 야구를 볼 때마다 텍사스에서의 시절이 생각난다.", en: "Watching baseball on TV always takes me back to my time in Texas.", source: "Day 087 교재3", meaning: meanings["take back_4"] },
        // Week 18 - take off
        { week: 18, ko: "포켓몬 고 열풍이 불었을 때 다 큰 어른들이 길을 걸으면서 포켓몬을 보던 거 기억해 봐요.", en: "Remember when Pokemon GO took off, and grown men were walking down the streets looking for Pokemon.", source: "Day 088 교재1", meaning: meanings["take off_4"] },
        { week: 18, ko: "바지 두 벌 사면 15% 빼 준대.", en: "If I buy two pairs of pants, they'll take 15% off.", source: "Day 088 교재1", meaning: meanings["take off_6"] },
        { week: 18, ko: "너는 안경 벗으면 완전 딴 사람 같아 보여.", en: "You look like a different person when you take off your glasses.", source: "Day 088 교재1", meaning: meanings["take off_1"] },
        { week: 18, ko: "태풍으로 인해 6시간 동안 연착이 된 터라, 15분 후에 비행기가 이륙한다는 기장의 안내 방송은 너무나 다행스러웠다.", en: "After a six-hour typhoon delay, it was such a relief to hear the captain announce that the plane was going to take off in 15 minutes.", source: "Day 088 교재1", meaning: meanings["take off_2"] },
        { week: 18, ko: "우리는 지금 출발하려고 해. 그래야 영화관에 늦지 않게 도착할 수 있어.", en: "We're going to take off so we can make it to the movie on time.", source: "Day 088 교재1", meaning: meanings["take off_3"] },
        { week: 18, ko: "탕후루가 몇 달 동안 엄청나게 인기였는데, 이제 인기가 시들해지고 있어.", en: "Tanghuru really took off for a few months, but it's starting to lose popularity.", source: "Day 088 교재1", meaning: meanings["take off_4"] },
        { week: 18, ko: "이 물건들은 선반에서 빼야 합니다. 유통기한이 지났어요.", en: "We need to take these items off the shelf. They're expired.", source: "Day 088 교재1", meaning: meanings["take off_5"] },
        { week: 18, ko: "현금으로 결제하시면 10달러를 더 빼 드리겠습니다.", en: "If you pay in cash, we will take an additional ten dollars off.", source: "Day 088 교재1", meaning: meanings["take off_6"] },
        { week: 18, ko: "미안해, 근데 지금 일어나 봐야 해. 남편이 식당에서 기다리고 있어서 말이야.", en: "Sorry, but I have to take off now. My husband is waiting for me at the restaurant.", source: "Day 088 교재2", meaning: meanings["take off_3"] },
        { week: 18, ko: "K팝과 K드라마가 본격적으로 인기를 끈 게 이제 겨우 몇 년이라서, 나는 아직은 크게 걱정 안 해.", en: "It's been only a couple of years since K-pop and K-dramas really took off, so I'm not too worried about it yet.", source: "Day 088 교재2", meaning: meanings["take off_4"] },
        { week: 18, ko: "팀장이 마지막 순간에 나를 최종 후보군에서 빼 버렸어.", en: "My team leader took me off the shortlist of candidates at the last minute.", source: "Day 088 교재2", meaning: meanings["take off_5"] },
        { week: 18, ko: "(판매자가 있는) 신사동에 가서 직접 픽업하겠다고 했더니 3만 원을 더 빼 주었다!", en: "Since I offered to go to Sinsa-dong and get them myself, he even took off an extra 30,000!", source: "Day 088 교재3", meaning: meanings["take off_6"] },
        // Week 18 - take on
        { week: 18, ko: "여름 여행 계획 짜는 건 내가 맡을 수 있을 것 같아.", en: "I think I could take on planning our trip for next summer.", source: "Day 089 교재1", meaning: meanings["take on_2"] },
        { week: 18, ko: "휴가철을 맞아 추가 직원을 뽑는데, 혹시 겨울방학 동안 아르바이트할 사람 알고 있어?", en: "We're taking on additional staff for the holiday season. Do you know anyone who'd want a part-time job over winter vacation?", source: "Day 089 교재1", meaning: meanings["take on_3"] },
        { week: 18, ko: "대학생들이 많은 빚을 지게 되는 건 너무 흔한 일이다. 이 방법 말고는 폭등한 등록금을 마련할 길이 없다.", en: "It's all too common for college students to take on lots of debt. There's pretty much no other way to come up with the inflated tuition.", source: "Day 089 교재1", meaning: meanings["take on_2"] },
        { week: 18, ko: "아시안컵에서 한국이 이란과 붙었다. 아쉽게도 지고 말았다.", en: "Korea took on Iran in the Asian cup, and unfortunately lost.", source: "Day 089 교재1", meaning: meanings["take on_1"] },
        { week: 18, ko: "이제 주장이 되었으니 더 많은 리더 역할을 맡아야 할 것 같습니다.", en: "Now that I'm the team captain, I'll have to take on more leadership duties.", source: "Day 089 교재1", meaning: meanings["take on_2"] },
        { week: 18, ko: "내가 일을 너무 많이 떠맡았어. 이 프로젝트 좀 도와줄 수 있을까?", en: "I have taken on too much work. Can you please help me with this project?", source: "Day 089 교재1", meaning: meanings["take on_2"] },
        { week: 18, ko: "추가 학생은 못 받을 것 같네요. 이미 제가 편하게 감당할 수 있는 학생 수를 넘어섰어요.", en: "I don't think I could possibly take on anyone else. I already have more students than I'm comfortable with.", source: "Day 089 교재1", meaning: meanings["take on_3"] },
        { week: 18, ko: "그녀는 남자 친구와 있을 때 딴사람이 된다.", en: "She takes on a different personality when she is with her boyfriend.", source: "Day 089 교재1", meaning: meanings["take on_4"] },
        { week: 18, ko: "좋아, 학교 마치고 내가 1 대 1로 상대해주겠다고 전해 줘.", en: "Sure, tell him I'll take him on 1-on-1 after school.", source: "Day 089 교재2", meaning: meanings["take on_1"] },
        { week: 18, ko: "한꺼번에 여러 가지 일을 맡는 건 이해는 됩니다. 하지만 많은 분이 눈치채셨겠지만, 한 번에 감당할 수 있는 일은 한계가 있습니다.", en: "While taking on multiple projects makes sense, a lot of you out there have probably figured out that there is only so much you can handle at one time.", source: "Day 089 교재3", meaning: meanings["take on_2"] },
        // Week 18 - take out
        { week: 18, ko: "나가는 길에 쓰레기 좀 버려 줄 수 있어?", en: "Can you take out the garbage on your way out?", source: "Day 090 교재1", meaning: meanings["take out_1"] },
        { week: 18, ko: "그분들이 청담에 있는 고급 식당에 가서 식사 대접을 해 주더군요.", en: "They took me out to a fancy restaurant in Cheongdam.", source: "Day 090 교재1", meaning: meanings["take out_3"] },
        { week: 18, ko: "이 아파트를 사기 위해 대출을 좀 받아야만 했습니다.", en: "I had to take out some loans to buy this apartment.", source: "Day 090 교재1", meaning: meanings["take out_4"] },
        { week: 18, ko: "이 문장은 빼세요. 전체 내용과 어울리지 않네요.", en: "I want you to take out this line. It looks out of place with the rest.", source: "Day 090 교재1", meaning: meanings["take out_1"] },
        { week: 18, ko: "차를 (전시장에서) 가지고 나가서 한 바퀴 돌아 봤는데요. 성능이 끝내주더군요.", en: "I took it out for a spin and was blown away by its performance.", source: "Day 090 교재1", meaning: meanings["take out_2"] },
        { week: 18, ko: "음식물 쓰레기를 내다 버리는 건 제일 하기 싫은 집안일이다.", en: "Taking out the food waste is my least favorite house chore.", source: "Day 090 교재1", meaning: meanings["take out_1"] },
        { week: 18, ko: "모은 돈이 부족해서, 새 차 살 때 대출을 받아야만 했어요.", en: "I didn't have enough saved up, so I had to take out a loan to buy my new car.", source: "Day 090 교재1", meaning: meanings["take out_4"] },
        { week: 18, ko: "나한테 화풀이하지 마!", en: "Don't take your anger out on me!", source: "Day 090 교재1", meaning: meanings["take out_5"] },
        { week: 18, ko: "부모님이 서울에 계실 동안 모시고 나가서 저녁 식사를 대접할까하는데, 서울역 근처에 괜찮은 식당 알아?", en: "I was thinking of taking my parents out to dinner while they are in town. Do you know of any nice places near Seoul Station?", source: "Day 090 교재1", meaning: meanings["take out_3"] },
        { week: 18, ko: "광흥창역 바로 옆에 괜찮은 양고기 집에 모시고 가면 괜찮을 것 같은데.", en: "Maybe you could take them out to that nice lamb place right next to Gwangheungchang station.", source: "Day 090 교재2", meaning: meanings["take out_3"] },
        { week: 18, ko: "Jeff, 발표 자료에서 이 슬라이드는 빼면 어떨까요? 큰 의미가 없는 내용이라서 빼도 큰 상관없을 듯한데.", en: "Jeff, what do you think about taking this slide out of the presentation? It doesn't seem to add much value.", source: "Day 090 교재2", meaning: meanings["take out_1"] }
    ];
