# TASK H\W

1) select wordform, COUNT(*) as count FROM wordform GROUP BY wordform ORDER BY count DESC LIMIT 10;
2) select wordformid from wordform where wordformid ILIKE 'a%';
3) select * from work WHERE genretype = 'p';
4) select AVG(totalparagraphs) AS avg_paragraphs FROM work WHERE genretype = 't';
5) select work.* FROM work join paragraph ON work.workid = paragraph.workid WHERE paragraph.wordcount > (SELECT AVG(wordcount) 
FROM paragraph);
6) select character.charname, COUNT(wordform.wordformid) AS dialogue_count, work.title AS work_title
FROM character JOIN paragraph ON character.charid = paragraph.charid JOIN chapter ON paragraph.chapterid = chapter.chapterid
JOIN work ON chapter.workid = work.workid join wordform ON paragraph.paragraphid = wordform.paragraphid GROUP BY character.charid, work.title;
7) select AVG(character.speechcount) AS avg_speechcount FROM character JOIN paragraph ON character.charid = paragraph.charid
JOIN chapter ON paragraph.chapterid = chapter.chapterid JOIN work ON chapter.workid = work.workid where work.description = 
'Romeo and Juliet';
8) select section, sum(wordcount) AS total_words from paragraph GROUP BY section;
9) select distinct plaintext AS charname, occurences AS speechcount FROM wordform WHERE occurences between 15 AND 30;
10) select distinct chapter.workid, chapter.chapterid, chapter.section, chapter.chapter, chapter.description from chapter join 
work ON chapter.workid = work.workid where work.year >= 1601 AND work.year <= 1700;
11) select * FROM chapter where LOWER(description) ILIKE '%the%';
12) select distinct section from paragraph;
13) select chapter.chapterid, chapter.description, work.title AS work_title FROM chapter JOIN work ON chapter.workid = work.
workid;
14) select paragraph.paragraphnum, character.charname, count(paragraph.paragraphid) AS dialogue_count from paragraph join 
character ON paragraph.charid = character.charid GROUP BY paragraph.paragraphnum, character.charname;
15) select paragraph.paragraphnum, work.title AS work_title, work.year FROM paragraph JOIN chapter ON paragraph.chapterid = 
chapter.chapterid JOIN work ON chapter.workid = work.workid;


