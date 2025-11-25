using System;
using System.Collections.Generic;

namespace QuizSystem
{
    // ===== INTERFEJSY =====

    public interface IAnswer<T>
    {
        T Value { get; }
        bool IsCorrect { get; }
    }

    public interface IQuestion<T>
    {
        string Text { get; }
        IReadOnlyList<IAnswer<T>> Answers { get; }
        void AddAnswer(IAnswer<T> answer);
    }

    public interface IQuiz<T>
    {
        string Title { get; }
        IReadOnlyList<IQuestion<T>> Questions { get; }
        void AddQuestion(IQuestion<T> question);
    }

    // ===== IMPLEMENTACJE =====

    public class Answer<T> : IAnswer<T>
    {
        public T Value { get; }
        public bool IsCorrect { get; }

        public Answer(T value, bool isCorrect)
        {
            Value = value;
            IsCorrect = isCorrect;
        }
    }

    public class Question<T> : IQuestion<T>
    {
        public string Text { get; }
        private readonly List<IAnswer<T>> _answers = new();
        public IReadOnlyList<IAnswer<T>> Answers => _answers;

        public Question(string text) => Text = text;

        public void AddAnswer(IAnswer<T> answer) => _answers.Add(answer);
    }

    public class Quiz<T> : IQuiz<T>
    {
        public string Title { get; }
        private readonly List<IQuestion<T>> _questions = new();
        public IReadOnlyList<IQuestion<T>> Questions => _questions;

        public Quiz(string title) => Title = title;

        public void AddQuestion(IQuestion<T> question) => _questions.Add(question);
    }

    // ===== PROGRAM =====

    class Program
    {
        static void Main()
        {

        }
    }
}
